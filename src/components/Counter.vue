<template>
    <div>
        <h1 @click="addOne">{{ counter }}</h1>
        <h2>{{ cheese }}</h2>
        <h3 v-for="num of arr" :key="num">{{ num }}</h3>
    </div>
</template>

<script>
import { ref } from "vue"

export default {
    name: "Counter",
    props: ["cheese"],
    // newer alt way using composition API
    // resembles react hooks
    setup(){
        const counter = ref(0)
        const addOne = () => counter.value += 1
        const arr = ref([1,2,3,4])
        return {counter, addOne, arr}
    }
    // og way using options API 
    // data: function(){
    //     return {
    //         counter: 0
    //     }
    // },
    // methods: {
    //     addOne: function(){
    //         this.counter += 1
    //     }
    // }
}
</script>

<style lang="scss">

</style>