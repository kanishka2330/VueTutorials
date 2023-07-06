<template>
    <div>
        <div>
            <input type="text" v-model="firstName">
            <input type="text" v-model="lastName">
            <person-greeting :firstName="firstName" :lastName="lastName"></person-greeting>
        </div>
    </div>
</template>

<script>
import {ref} from 'vue'
import personGreeting from './personGreeting.vue'
    export default {
        components: { personGreeting },
        name: "personComponent",
        setup(){
            const firstName = ref('')
            const lastName = ref('')
            return{
                firstName,
                lastName
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>