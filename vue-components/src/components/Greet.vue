<template>
    <div>
        It is always {{this.hero}} 
        <div v-bind="$attrs"> and {{this.heroine}}</div>
        <div>at age {{age}}</div>
    </div>
</template>

<script>
    export default {
        name: 'GreetComponent',
        props: {
            hero: {
                type: String,
                required: true
            },
            heroine: {
                type: String
            },
            age:{
                type: Number,
                default: 40
            }
        },
        inheritAttrs: false
    }
</script>

<style lang="scss" scoped>

</style>