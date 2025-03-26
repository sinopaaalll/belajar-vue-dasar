<script setup>
    import { ref } from "vue";
    import Counter from "./Counter.vue";
    import CounterStateless from "./CounterStateless.vue";

    const counter = ref(0);

    function increment(value){
        counter.value += value;
    }
</script>

<template>
    <h1>Counter Naufal</h1>
    <Counter name="Naufal" initial-count="10"/>
    <Counter name="Rz" initial-count="20"/>

    <CounterStateless name="Oke" :counter="counter" :increment="1" @click="increment" />
    <CounterStateless name="Moro" :counter="counter" :increment="2" @click="increment" />


</template>