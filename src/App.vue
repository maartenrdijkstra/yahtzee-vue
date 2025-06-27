<template>
  <ThrownDice v-model="dice"></ThrownDice>
  <ScoreTable v-model="dice"></ScoreTable>
</template>

<script setup>
import ThrownDice from "./components/ThrownDice.vue";
import ScoreTable from "./components/ScoreTable.vue";

const dice = [];
</script>

<style scoped></style>
