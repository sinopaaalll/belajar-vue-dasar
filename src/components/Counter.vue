<template>
    <div>
        <h1 id="count">Counter {{ counter.name }} : {{ counter.count }}</h1>
        <button v-on:click="increment">Increment</button>
    </div>
</template>

<script setup>
import { nextTick, ref } from "vue";

console.info(`Load Component`);
let counter = ref({
    count: 0,
    name: "Naufal",
});


async function increment() {
    console.info(`Increment counter : ${counter.value.count}`);
    counter.value = {
        name: counter.value.name,
        count: counter.value.count + 1,
    };

    await nextTick();

    console.log("Increment count after nextTick");
};
</script>

<style scoped>

</style>