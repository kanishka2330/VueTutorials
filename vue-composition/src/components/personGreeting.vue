<template>
    <div>
        <div> Hello {{fullname}}</div>
    </div>
</template>

<script>
import {computed} from 'vue'
    export default {
        name: "personGreeting",
        props: ['firstName', 'lastName'],
        // computed: {
        // fullname(){
        //     return `${this.firstName} ${this.lastName}`
        // }
        setup(props){
                const computedComposition  = computed(() => {
                    return `${props.firstName} ${props.lastName}`
                })
            }
            return{
                fullName,
            }
        }

</script>

<style lang="scss" scoped>

</style>