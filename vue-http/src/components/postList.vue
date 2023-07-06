<template>
    <div>
        <form @submit.prevent="sendData">
        <label for="title">Title</label>
        <input type="text" v-model="formData.title">
        <label for="body">Body</label>
        <input type="text" v-model="formData.body">
        <label for="userId">UserId</label>
        <input type="text" v-model="formData.userId">
        <hr>
        <!-- <button @click="getPosts">Load Posts </button> -->
        <button @click="sendData">Send Data</button>
        <div v-if="errorMsg">{{errorMsg}}</div>
        <div v-for="post in posts" :key="post.id">
            <h3>{{post.id}}</h3>
            <h2>{{post.title}}</h2>
            <p>{{post.body}}</p>
        </div>
        </form>
    </div>
</template>

<script>
import axios from 'axios'
    export default {
        name: "postList",
        created() {
            this.getPosts()
        },
        data() {
            return {
                posts: [],
                formData: {
                    title: '',
                    body: '',
                    userId:'',
                },
                errorMsg: '',
            }
        },
        methods: {
            getPosts() {
                axios
                .get('https://jsonplaceholder.typicode.com/posts')
                .then((response)=>{
                    this.posts = response.data
                })
                .catch((error)=>{
                    this.errorMsg = error
                })
            },
            sendData() {
                axios
                .post('https://jsonplaceholder.typicode.com/posts',
                    this.formData)
                .then((response)=>{
                    console.log(response);
                    this.posts = response.data
                })
                .catch((error)=>{
                    console.log(error)
                    this.errorMsg = error
                })
            },
        },
    }
</script>

<style lang="scss" scoped>

</style>