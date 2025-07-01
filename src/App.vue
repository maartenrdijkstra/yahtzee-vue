<template>
    <ThrownDice v-model="dice"></ThrownDice>
    <ScoreTable v-model="dice"></ScoreTable>
</template>

<script setup>
import ThrownDice from './components/ThrownDice.vue';
import ScoreTable from './components/ScoreTable.vue';
import {ref} from 'vue';

const dice = ref([]);
</script>

<style scoped></style>
