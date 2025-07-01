<template>
    <button @click="rollDice">Gooien!</button>

    <table class="dice-table">
        <tr v-for="(rolledDice, index) in dice" :key="index">
            <td>{{ rolledDice }}</td>
        </tr>
    </table>
</template>

<script setup>
import {ref} from 'vue';

const dice = defineModel();

const rollDice = () => {
    dice.value.splice(0, dice.value.length);
    for (let i = 0; i < 5; i++) {
        const thrownDice = Math.trunc(Math.random() * 6) + 1;
        dice.value.push(thrownDice);
    }
};
</script>
