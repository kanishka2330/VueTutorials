<template>
    <div>
        <h2>Parent Component {{name}}</h2>
        <h2>Parent refLaugh {{refLaugh}}</h2>
        <h2>Parent reactiveSmile {{reactiveSmile}}</h2>
        <button @click="changeReactiveSmile">Change the way you smile</button>
        <child-a/>
    </div>
</template>

<script>
import {provide, toRefs, reactive, ref} from 'vue'
import childA from './childA.vue'
    export default {
        name: 'provideInject',
        components: {
            childA
        },
        setup(){
          provide('c_username', 'Taaaashi')
          const refLaugh = ref("YouLookGood")
          const state = reactive({
            reactiveSmile: 'Kanishkaaaaaaaaa'
          })
          provide('c_refLaugh', refLaugh)
          provide('c_state', state)
          provide('changeReactiveSmileFunction', changeReactiveSmile)
          function changeReactiveSmile() {
                // reactiveSmile: "The smile has been changed"
                refLaugh.value = " " + "You look better"
          }
          return{
            refLaugh,
            ...toRefs(state),
            changeReactiveSmile
          }
        },
        data() {
            return{
                name: 'Kanishka'
            }
        },
        provide(){
            return{
                username: this.name,
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>