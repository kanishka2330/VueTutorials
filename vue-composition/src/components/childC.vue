<template>
    <div>
        <div>Child C component</div>
        <div>Injected : {{username}}</div>
        <div>Child Username {{childUsername}}</div>
        <div>Child Laugh {{childLaugh}}</div>
        <div>Child State smile {{reactiveSmile}}</div>
        <button @click="changeTheWayYouSmile">Change the way you smile from child</button>
    </div>
</template>

<script>
import {inject, toRefs} from 'vue'
    export default {
        name:'ChildC',
        setup(){
            const childLaugh = inject('c_refLaugh')
            const stateSmile = inject('c_state')
            const childUsername = inject('c_username', 'Default username')
            const changeTheWayYouSmile = inject('changeReactiveSmileFunction')
            return{
                childUsername,
                ...toRefs(stateSmile),
                childLaugh,
                changeTheWayYouSmile
            }
        },
        inject: ['username'],
    }
</script>

<style scoped>

</style>