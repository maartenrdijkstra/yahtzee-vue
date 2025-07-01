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
            <tr v-for="(score, key) in singleScores" :key="key">
                <td class="text-align-left" colspan="2">{{ numberWords[key] }}</td>
                <td class="text-align-right">Tel alle {{ numberWords[key] }}</td>
                <td>{{ score }}</td>
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
                <td>{{ totalUpperMinusBonus }}</td>
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
                <td>{{ bonus }}</td>
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
                <th>{{ totalUpperPlusBonus }}</th>
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
                <td class="text-align-right">Totaal v.d. 3 stenen</td>
                <td>{{ threeOfAKind }}</td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td class="text-align-left">Carré</td>
                <td class="text-align-right">4 dezelfde</td>
                <td class="text-align-right">Totaal v.d. 4 stenen</td>
                <td>{{ fourOfAKind }}</td>
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
                <td>{{ fullHouse }}</td>
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
                <td>{{ smallStraight }}</td>
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
                <td>{{ largeStraight }}</td>
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
                <td>{{ topScore }}</td>
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
                <td>{{ chance }}</td>
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
                <td>{{ totalLower }}</td>
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
                <td>{{ totalUpperPlusBonus }}</td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <th class="text-align-left" colspan="2">Totaal Generaal</th>
                <th class="text-align-right">&rightarrow;</th>
                <th>{{ totalGeneral }}</th>
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
import {ref, computed} from 'vue';
const dice = defineModel();

const numberWords = ref({
    1: 'Enen',
    2: 'Tweeën',
    3: 'Drieën',
    4: 'Vieren',
    5: 'Vijven',
    6: 'Zessen',
});

const count = computed(() => {
    const countObj = {
        1: 0,
        2: 0,
        3: 0,
        4: 0,
        5: 0,
        6: 0,
    };

    dice.value.forEach(dice => {
        countObj[dice]++;
    });

    return countObj;
});

const singleScores = computed(() => {
    const countObj = {
        1: 0,
        2: 0,
        3: 0,
        4: 0,
        5: 0,
        6: 0,
    };

    Object.keys(count.value).forEach(key => {
        countObj[key] = count.value[key] * key;
    });

    return countObj;
});

const totalUpperMinusBonus = computed(
    () =>
        singleScores.value[1] +
        singleScores.value[2] +
        singleScores.value[3] +
        singleScores.value[4] +
        singleScores.value[5] +
        singleScores.value[6],
);

const bonus = computed(() => (totalUpperMinusBonus.value >= 63 ? 35 : 0));
const totalUpperPlusBonus = computed(() => (totalUpperMinusBonus.value >= 63 ? totalUpperMinusBonus.value + 35 : 0));
const threeOfAKind = computed(() => (xOfAKind(3) || xOfAKind(4) || xOfAKind(5) ? countTotalEyes() : 0));
const fourOfAKind = computed(() => (xOfAKind(4) || xOfAKind(5) ? countTotalEyes() : 0));
const fullHouse = computed(() => (checkFullHouse() ? 25 : 0));
const smallStraight = computed(() => (checkStraight(4) || checkStraight(5) ? 30 : 0));
const largeStraight = computed(() => (checkStraight(5) ? 40 : 0));
const topScore = computed(() => (xOfAKind(5) ? 50 : 0));
const chance = computed(() => countTotalEyes());
const totalLower = computed(
    () =>
        threeOfAKind.value +
        fourOfAKind.value +
        fullHouse.value +
        smallStraight.value +
        largeStraight.value +
        topScore.value +
        chance.value,
);
const totalGeneral = computed(() => totalUpperPlusBonus.value + totalLower.value);

function countTotalEyes() {
    return dice.value.reduce((acc, currValue) => acc + currValue, 0);
}

function checkFullHouse() {
    const countSameEyes = {};
    for (const d of dice.value) {
        countSameEyes[d] = (countSameEyes[d] || 0) + 1;
    }

    const values = Object.values(countSameEyes).sort((a, b) => a - b);

    return JSON.stringify(values) === JSON.stringify([2, 3]);
}

function xOfAKind(numberToSearchFor) {
    for (let d in count.value) {
        if (count.value[d] === numberToSearchFor) {
            return true;
        }
    }
    return false;
}

function checkStraight(seriesTotal) {
    let teller = 0;
    console.log(count.value);

    for (const d in count.value) {
        if (count.value[d] > 0) {
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
