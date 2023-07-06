<template>
    <div>
        <h2>{{firstName}} {{lastName}}</h2>
    </div>
</template>

<script>
import {reactive, toRefs} from 'vue'
    export default {
        name: "Demo2Component",
        setup() {
            const state = reactive({
                firstName: 'Bruce',
                lastName: 'Wayne'
            })

            setTimeout(()=>{
                state.firstName = 'Ariana'
                state.lastName = 'Grande'
                console.log(state)
            }, 2000)

            return toRefs(state)

                // firstName: state.firstName (since individual property is returned, vue does not track changes made to it )

        }
    }
</script>

<style lang="scss" scoped>

</style>