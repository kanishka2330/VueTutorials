<template>
    <div>
        <input type="text" placeholder="Firstname" v-model="fname">
        <input type="text" placeholder="Lastname" v-model="lname">
        <div>
            Options : {{fullName}}
        </div>
        <input type="text" placeholder="RefFirstname" v-model="refFirstName">
        <input type="text" placeholder="RefLastname" v-model="refLastName">
        <div>
            Composition Ref : {{refFullName}}
        </div>
        <input type="text" placeholder="School Name" v-model="school">
        <input type="text" placeholder="City Name" v-model="city">
        <div>
            Composition Reactive : {{reactiveFullName}}
        </div>

    </div>
</template>

<script>
import {ref, computed, reactive, toRefs} from 'vue'
    export default {
        name: "computedComponent",
        setup() {
            const refFirstName = ref('')
            const refLastName = ref('')

            const refFullName = computed(function(){
                return `${refFirstName.value} ${refLastName.value}`
            })

            const state = reactive({
                school: '',
                city: ''
            })

            const reactiveFullName = computed(function(){
                return `${state.school} ${state.city}`
            })

            return{
                refFirstName,
                refLastName,
                refFullName,
                reactiveFullName,
                ...toRefs(state)
            }
        },
        data(){
            return{
                fname: '',
                lname: ''
            }
        },
        computed: {
            fullName(){
            return `${this.fname} ${this.lname}`
            },
        }
    }
</script>

<style scoped>

</style>