<template>
    <h1>Contact Form</h1>
    <form>
        <div>
            <label for="name">Name:
                <input type="text" name="name" id="name" v-model="model.name">
            </label>
        </div>
        <div>
            <label for="email">Email:
                <input type="email" name="email" id="email" v-model="model.email">
            </label>
        </div>
        <div>
            <label for="age">Age:
                <input type="number" name="age" id="age" v-model.number="model.age">
            </label>
        </div>
        <div>
            <label for="type">Type:
                <select name="type" id="type" v-model="model.type">
                    <option value="Regular">Regular</option>
                    <option value="VIP">VIP</option>
                </select>
            </label>
        </div>
        <div>
            <label for="complain">Complain:
                <input type="checkbox" name="complain" id="complain" v-model="model.complain">
            </label>
        </div>
        <div>
            <label for="message">Message:
                <textarea name="complain" id="complain" v-model="model.message"></textarea>
            </label>
        </div>
    </form>
</template>

<script setup>
    const model = defineModel({
        required: true,
        default: {
            name: "",
            email: "",
            age: 0,
            type: "Regular",
            complain: false,
            message: "",
        },
        type: Object,
        get: (value) => {
            value.email = value.email.toUpperCase();
            return value;
        }
    });
</script>

<style scoped>

</style>