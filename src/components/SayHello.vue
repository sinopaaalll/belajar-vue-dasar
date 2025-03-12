<template>
    <div>
        <form>

            <button v-on:click="counter++">Increment {{ counter }}</button> <br />
            <input type="text" placeholder="First Name" id="firstName" @input="changesFirstName" /> <br/>
            <input type="text" placeholder="Last Name" id="lastName" @input="changesLastName" /> <br/>
            
            <button @click.prevent="sayHello">Say Hello</button>
        </form>
    </div>
    <h1>Hello {{ fullName }}</h1>
</template>

<script setup>
import { computed, reactive, ref } from 'vue';

const counter = ref(0);

const person = reactive({
    firstName: '',
    lastName: '',
});

const fullName = computed((oldName) => {
    console.log(`Changes old name, ${oldName}`);
    return `${person.firstName} ${person.lastName}`;
}) 

function sayHello() {
    person.firstName = document.getElementById('firstName').value;
    person.lastName = document.getElementById('lastName').value;
}

function changesFirstName(event) {
    person.firstName = event.target.value;
}

function changesLastName(event) {
    person.lastName = event.target.value;
}

</script>

<style scoped>

</style>