<template>
    <div>
        <div>Child B component</div>
        <child-c/>
    </div>
</template>

<script>
import childC from './childC.vue'
    export default {
        name:'ChildB',
        components: {
            childC
        },
    }
</script>

<style lang="scss" scoped>

</style>