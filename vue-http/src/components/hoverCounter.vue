<template>
  <div>
    <h2 @mouseover="incrementCounter">Hovered {{count}}</h2>
  </div>
</template>

<script>
import CounterMixin from '../mixins/counter'
export default {
  name: "hoverCounter",
  mixins: [CounterMixin]
};
</script>

<style lang="scss" scoped>
</style>