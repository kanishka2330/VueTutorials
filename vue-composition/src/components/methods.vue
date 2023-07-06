<template>
    <div>
        <h2>{{name}}</h2>
        <button @click="setName">Change name to Codevoultion</button>
        <h2>{{count}}</h2>
        <button @click="incrementCount">Increment Count</button>
        <h2>{{firstName}} {{lastName}}</h2>
        <button @click="changeHero">Change Hero</button>
    </div>
</template>

<script>
import {ref, reactive, toRefs} from 'vue'
    export default {
        name: "methodsComponent",
        data() {
            return {
                name: 'Vishwas'
            }
        },
        methods: {
            setName() {
                this.name = 'codevoultion'
            }
        },
        setup() {
            const count = ref(0)

            function incrementCount(){
                count.value++
            }

            const state = reactive({
                    firstName: 'Bruce',
                    lastName: 'Wayne'
                })

            function changeHero() {
                state.firstName = "Clark"
                state.lastName = "Kent"
            }
            return{
                count,
                incrementCount,
                changeHero,
                ...toRefs(state)
            }

        }
    }
</script>

<style lang="scss" scoped>

</style>