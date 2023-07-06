<template>
  <div>
    <button @click="incrementCounter">Clicked {{count}}</button>
  </div>
</template>

<script>
import CounterMixin from '../mixins/counter'
export default {
  name: "clickCounter",
  mixins: [CounterMixin]
};
</script>

<style lang="scss" scoped>
</style>