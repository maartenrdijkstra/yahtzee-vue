<template>
  <table class="scoreblok">
    <thead>
      <tr>
        <th class="text-align-left scoreblok-title" colspan="9">Scoreblok</th>
      </tr>
      <tr>
        <th class="text-align-left" colspan="2">Deel 1</th>
        <th colspan="1" class="text-align-right">Puntentelling</th>
        <th>1e spel</th>
        <th>2e spel</th>
        <th>3e spel</th>
        <th>4e spel</th>
        <th>5e spel</th>
        <th>6e spel</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="text-align-left" colspan="2">Enen</td>
        <td class="text-align-right">Tel alle Enen</td>
        <td class="upper">{{ enen }}</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td class="text-align-left" colspan="2">Tweeën</td>
        <td class="text-align-right">Tel alle Tweeën</td>
        <td class="upper">{{ tweeen }}</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td class="text-align-left" colspan="2">Drieën</td>
        <td class="text-align-right">Tel alle Drieën</td>
        <td class="upper">{{ drieen }}</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td class="text-align-left" colspan="2">Vieren</td>
        <td class="text-align-right">Tel alle Vieren</td>
        <td class="upper">{{ vieren }}</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td class="text-align-left" colspan="2">Vijven</td>
        <td class="text-align-right">Tel alle Vijven</td>
        <td class="upper">{{ vijven }}</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td class="text-align-left" colspan="2">Zessen</td>
        <td class="text-align-right">Tel alle Zessen</td>
        <td class="upper">{{ zessen }}</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td class="text-align-left">Totaal</td>
        <td class="text-align-right">aantal punten</td>
        <td class="text-align-right">&rightarrow;</td>
        <td class="upper">0</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td class="text-align-left">Bonus</td>
        <td class="text-align-right">Als puntentotaal 63 of meer is</td>
        <td class="text-align-right">35 punten</td>
        <td class="upper">0</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <th class="text-align-left">Totaal</th>
        <th class="text-align-right">van de bovenste helft</th>
        <th class="text-align-right">&rightarrow;</th>
        <th class="upper">0</th>
        <th></th>
        <th></th>
        <th></th>
        <th></th>
        <th></th>
      </tr>
      <th colspan="9" class="text-align-left">Deel 2</th>
      <tr>
        <td class="text-align-left">Three of a kind</td>
        <td class="text-align-right">3 dezelfde</td>
        <td class="text-align-right">Totaal v.d. 5 stenen</td>
        <td class="lower">0</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td class="text-align-left">Carré</td>
        <td class="text-align-right">4 dezelfde</td>
        <td class="text-align-right">Totaal v.d. 5 stenen</td>
        <td class="lower">0</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td class="text-align-left">Full House</td>
        <td class="text-align-right">2 + 3 dezelfde</td>
        <td class="text-align-right">25 punten</td>
        <td class="lower">0</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td class="text-align-left">Kleine straat</td>
        <td class="text-align-right">4 opeenvolgende nummers</td>
        <td class="text-align-right">30 punten</td>
        <td class="lower">0</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td class="text-align-left">Grote straat</td>
        <td class="text-align-right">5 opeenvolgende nummers</td>
        <td class="text-align-right">40 punten</td>
        <td class="lower">0</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td class="text-align-left">Topscore</td>
        <td class="text-align-right">5 dezelfde</td>
        <td class="text-align-right">50 punten</td>
        <td class="lower">0</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td class="text-align-left">Chance</td>
        <td class="text-align-right">vrije keus</td>
        <td class="text-align-right">Totaal v.d. 5 stenen</td>
        <td class="lower">0</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td class="text-align-left"><strong>Totaal</strong></td>
        <td class="text-align-right">van de onderste helft</td>
        <td class="text-align-right">&rightarrow;</td>
        <td class="lower">0</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td class="text-align-left"><strong>Totaal</strong></td>
        <td class="text-align-right">van de bovenste helft</td>
        <td class="text-align-right">&rightarrow;</td>
        <td class="lower">0</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <th class="text-align-left" colspan="2">Totaal Generaal</th>
        <th class="text-align-right">&rightarrow;</th>
        <th class="lower">0</th>
        <th></th>
        <th></th>
        <th></th>
        <th></th>
        <th></th>
      </tr>
    </tbody>
  </table>
</template>

<script setup>
import { ref, computed } from "vue";
const dice = defineModel();

let diceArr = [];

const count = ref({
  1: 0,
  2: 0,
  3: 0,
  4: 0,
  5: 0,
  6: 0,
});

function fillScoreFields(count, diceArr) {
  let totalUpperMinusBonusScore = 0;
  for (let i = 1; i <= 6; i++) {
    totalUpperMinusBonusScore += Number(count[i] * i);
  }
  totalUpperMinusBonus.textContent = totalUpperMinusBonusScore;

  if (totalUpperMinusBonusScore >= 63) {
    bonus.textContent = 35;
  } else {
    bonus.textContent = 0;
  }

  totalUpperPlusBonus.textContent =
    totalUpperMinusBonusScore + Number(bonus.textContent);

  let totalLowerPartScore = 0;
  for (field of lowerFields) {
    totalLowerPartScore += Number(field.textContent);
  }
  totalLowerPart.textContent = totalLowerPartScore;

  totalUpperPlusBonus2.textContent = totalUpperPlusBonus.textContent;

  totalGeneral.textContent =
    Number(totalLowerPart.textContent) +
    Number(totalUpperPlusBonus2.textContent);
}

function countTotalEyes(diceArr) {
  return diceArr.reduce((acc, currValue) => acc + currValue);
}

function checkFullHouse(diceArr) {
  const countSameEyes = {};
  for (const dice of diceArr) {
    countSameEyes[dice] = (countSameEyes[dice] || 0) + 1;
  }

  const values = Object.values(countSameEyes).sort((a, b) => a - b);

  return JSON.stringify(values) === JSON.stringify([2, 3]);
}

function xOfAKind(numberToSearchFor) {
  for (dice in count) {
    if (count[dice] === numberToSearchFor) {
      return true;
    }
  }
  return false;
}

function checkStraight(count, seriesTotal) {
  let teller = 0;
  console.log(count);

  for (dice in count) {
    if (count[dice] > 0) {
      teller++;
    } else {
      teller = 0;
    }
    if (teller === seriesTotal) {
      return true;
    }
  }
  return false;
}
const throwDice = () => {
  let thrownDice = 0;

  for (let index in count.value) {
    count.value[index] = 0;
  }

  for (let i = 0; i < 5; i++) {
    thrownDice = Math.trunc(Math.random() * 6) + 1;

    diceArr.push(thrownDice);

    count.value[thrownDice]++;
  }

  console.table(count.value);
};

const enen = computed(() => {
  console.log(count[1]);
  return Number(count[1] * 1);
});

const tweeen = computed(() => {
  return Number(count[2] * 1);
});

const drieen = computed(() => {
  return Number(count[3] * 1);
});

const vieren = computed(() => {
  return Number(count[4] * 1);
});

const vijven = computed(() => {
  return Number(count[5] * 1);
});

const zessen = computed(() => {
  return Number(count[6] * 1);
});
</script>

<style>
.container {
  margin: 10px 10px 0 16px;
  border: 2px solid #000;
  width: 1100px;
}

.text-align-left {
  text-align-last: left;
}

.text-align-right {
  text-align: right;
}

.scoreblok {
  border: collapse;
  border-spacing: 0;
}

td,
th {
  padding: 7px 8px;
}

.scoreblok {
  margin: 0 auto 20px;
}

.scoreblok td {
  border-bottom: 1px solid #aaa;
}

.scoreblok th {
  border-bottom: 2px solid #333;
}

.btn {
  margin: 16px;
  padding: 12px 24px;
  font-size: 24px;
  border-radius: 100px;
}

.dice-table {
  margin: 16px 16px 0px 16px;
  font-weight: bold;
  font-size: 32px;
  height: 120px;
  display: flex;
  justify-content: center;
}

.dice-table td {
  padding-right: 32px;
}

.scoreblok-title {
  font-size: 24px;
}

.flex-container img {
  width: 20%;
  margin-bottom: -20px;
  margin-right: 16px;
}

.flex-container {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
}
</style>
