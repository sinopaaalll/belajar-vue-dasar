<template>
        <h1>Todo List</h1>
        <template v-for="item in items">
            <ul v-if="!item.done" :key="item.id">
                <li v-for="(value, key) in item" :key="key">
                    {{ key }} : {{ value }}
                </li>
            </ul>
        </template>

    <div v-for="n in 10">
        <h1>Hello {{ n }}</h1>
    </div>
</template>

<script setup>
const items = [{
    id: 1,
    text: "Learn Vue 3",
    done: true
}, {
    id: 2,
    text: "Learn Vue Router",
    done: false
}, {
    id: 3,
    text: "Learn Pinia",
    done: false
}];
</script>

<style scoped>

</style>