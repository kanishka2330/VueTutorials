<template>
    <div>
        This is component B
        <component-c/>
    </div>
</template>

<script>
import componentC from './componentC.vue'
    export default {
        name: "componentB",
        components: {
            componentC
        }
    }
</script>

<style lang="scss" scoped>

</style>