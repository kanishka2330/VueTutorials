<template>
    <div>
        This is component C
        <div>Injected {{name}}</div>
    </div>
</template>

<script>
    export default {
        name: "componentC",
        inject: [
            'name',
        ]
    }
</script>

<style lang="scss" scoped>

</style>