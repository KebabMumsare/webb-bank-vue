<script setup>
import { useStorage } from '@vueuse/core';
import { ref } from "vue";

    const users = useStorage('users', []);

    const name = ref("");
    const amount = ref("");

    function add() {
        users.value.push({
            name: name,
            amount: amount,
        })
    }
</script>
<template>
    <form>
        <input type="text" v-model="name">
        <input type="number" v-model="amount">
        <button @click="add">Lägg till</button>
    </form>
    <div v-for="user of users">
        {{user.name}}
        <br>
        {{user.amount}}
    </div>
</template>