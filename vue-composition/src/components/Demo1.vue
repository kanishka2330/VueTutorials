<template>
    <div>
       <h2>{{name}}</h2> 
    </div>
</template>

<script>
import {ref} from 'vue'
    export default {
        name: "Demo1Component",
        setup() {
            const name = ref('Vishwas')

            setTimeout(()=>{
                name.value = 'Codevoultion',
                console.log(name)
            }, 2000)

            return{
                name
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>