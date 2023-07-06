<template>
    <div>
        <input type="text" placeholder="First Name" v-model="fname">
        <input type="text" placeholder="Last Name" v-model="lname">
        <input type="text" placeholder="Hero Name" v-model="heroName">
        <input type="text" placeholder="ID" v-model="id">
        <input type="text" placeholder="Department" v-model="department">
    </div>
</template>

<script>
import {ref, toRefs, reactive} from 'vue'
    export default {
        name: 'vModel',
        setup() {
            const heroName = ref('')
            const state = reactive({
                id: ' ',
                department: ' '
            })

            return{
                heroName,
                ...toRefs(state)
            }
        },
        data(){
            return {
                fname: '',
                lname: ''
            }
        }
    }
</script>

<style scoped>

</style>