<template>
    <label for="productId">
        Product Id :
        <select name="" id="" v-model="productId">
            <option value=""></option>
            <option value="product1">Product 1</option>
            <option value="product2">Product 2</option>
            <option value="product3">Product 3</option>
        </select>
    </label>
    <div v-if="product">
    <ProductDetail :id="product.id" :price="product.price" :name="product.name"/>
        <!-- <h1>Product</h1>
        <p>Id : {{ product.id }}</p>
        <p>Name : {{ product.name }}</p>
        <p>Price : {{ product.price }}</p> -->
    </div>
</template>

<script setup>
import ProductDetail from "./ProductDetail.vue";
import { onWatcherCleanup, ref, watch, watchEffect } from 'vue';

const productId = ref("product1");
const product = ref(null);

// watch(productId, async (newVal, oldVal) => {
//     console.log(`call watch callback`);
//     const response = await fetch(`/${newVal}.json`);
//         product.value = await response.json();
// }, {
//     immediate: true
// })

// watchEffect(async () => {
//     console.log(`call watch callback`);
//     const response = await fetch(`/${productId.value}.json`);
//     product.value = await response.json();
// })

watchEffect(async () => {
    onWatcherCleanup(() => {
        console.log(`cleanup`);
    });

    console.log(`call watch callback`);
    const response = await fetch(`/${productId.value}.json`);
    product.value = await response.json();
})
</script>

<style scoped>

</style>