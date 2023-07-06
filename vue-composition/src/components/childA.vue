<template>
    <div>
        <div>Child A component</div>
        <child-b/>
    </div>
</template>

<script>
import childB from './childB.vue'
    export default {
        name:"childA",
        components: {
            childB
        },
    }
</script>

<style lang="scss" scoped>

</style>