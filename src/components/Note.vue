<script setup>
import { onBeforeMount, onMounted, onUpdated, reactive, ref, useTemplateRef } from 'vue';

const notes = reactive([]);
const note = ref("");
const noteInput = useTemplateRef('noteInput');
const noteList = useTemplateRef('noteList');

function addNote() {
    notes.push(note.value);
    note.value = "";
    noteInput.value.focus();
    if (noteList.value) {
        noteList.value.forEach((li) => {
            console.info(li.textContent);
        })
    }
}

onBeforeMount(() => {
    console.info('onBeforeMount');
});

onMounted(() => {
    console.info('onMounted');
})

onUpdated(() => {
    console.info('onUpdated');
})

</script>

<template>
    <h1>Buat Note</h1>
    <div>
        <input type="text" ref="noteInput" v-model="note" placeholder="Tulis note disini"> <br>
        <button @click="addNote">Tambah Note</button>
    </div>

    <h1>Daftar Note</h1>
    <ul>
        <li v-for="note in notes" ref="noteList">
            {{ note }}
        </li>
    </ul>
</template>

<style scoped>

</style>