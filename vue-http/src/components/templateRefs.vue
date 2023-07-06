<template>
    <div>
        <input type="text" ref="inputRef">
        <post-list ref="postListRef"></post-list>
    </div>
</template>

<script>
import postList from "./postList.vue";
    export default {
        name: "templateRef",
        components: {
            postList,
        },
        mounted() {
            console.log(this.$refs.postListRef)
            this.$refs.inputRef.focus()
        }
    }
</script>

<style lang="scss" scoped>

</style>