<template>
    <h1>Score APP</h1>
    <div v-show="score > 50">
        <p>Score is {{ score }}</p>
    </div>
    <div v-if="score > 90">
        Yay cool score {{ score }}
    </div>
    <div v-else-if="score > 70">
        Good score {{ score }}
    </div>
    <div v-else>
        Ups, bad score {{ score }}
    </div>
</template>

<script setup>
import { ref } from 'vue';

const score = ref(40);
</script>

<style scoped>

</style>