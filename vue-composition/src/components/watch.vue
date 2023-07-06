<template>
    <div>
        <input type="text" placeholder="name" v-model="name">
        <input type="text" placeholder="refName" v-model="refName">
        <input type="text" placeholder="refLastName" v-model="refLastName">
        <input type="text" placeholder="reactiveSchool" v-model="school">
        <input type="text" placeholder="reactiveCity" v-model="city">
        <input type="text" placeholder="reactiveHeroname" v-model="options.heroName">
    </div>
</template>

<script>
import _ from 'lodash'
import {ref, watch, reactive, toRefs} from 'vue'
    export default {
        name: "watchComponent",
        setup(){
            const state = reactive({
                school: '',
                city: '',
                options: {
                    heroName: ''
                }
            })
            // watch(()=>{
            //     return {...state}
            // }, function(newValue, oldValue){
            //     console.log('reactiveSchoolNewValue', newValue.school)
            //     console.log('reactiveSchoolOldValue', oldValue.school)
            //     console.log('reactiveCityOldValue', oldValue.city)
            //     console.log('reactiveCityOldValue', oldValue.city)
            // })
            watch(()=>_.cloneDeep(state.options), function(newValue, oldValue){
                console.log('schoolNewValue', newValue)
                console.log('schoolOldValue', oldValue)
            },{
                deep: true
            })
            const refName = ref('')
            const refLastName = ref('')
            watch([refName,refLastName], (newValues, oldValues)=>{
                console.log('refNewValue', newValues[0])
                console.log('refOldValue', oldValues[0])
                console.log('refLastNameNewValue', newValues[1])
                console.log('refLastNameOldValue', oldValues[1])
            }, {
                immediate: true
            })
            return{
                refName,
                refLastName,
                ...toRefs(state)
            }
        },
        data() {
            return{
                name: '',
            }
        },
        watch:{
            name(newValue, oldValue){
                console.log('newValue', newValue)
                console.log('oldValue', oldValue)
            }
        }
    }
</script>

<style scoped>

</style>