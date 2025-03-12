<template>
    <h1>Buat Note</h1>
    <div>
        <input type="text" ref="noteInput" v-model="note" placeholder="Tulis note disini"> <br>
        <button @click="addNote">Tambah Note</button>
    </div>

    <h1>Daftar Note</h1>
    <ul>
        <li v-for="note in notes" :key="note">
            {{ note }}
        </li>
    </ul>
</template>

<script setup>
import { reactive, ref, useTemplateRef } from 'vue';

const notes = reactive([]);
const note = ref("");
const noteInput = useTemplateRef('noteInput');

function addNote() {
    notes.push(note.value);
    note.value = "";
    noteInput.value.focus();
}

</script>

<style scoped>

</style>