<template>
    <div>
        This is component A
        <component-b/>
    </div>
</template>

<script>
import componentB from './componentB.vue'
    export default {
        name: "componentA",
        components: {
            componentB,
        }
    }
</script>

<style lang="scss" scoped>

</style>