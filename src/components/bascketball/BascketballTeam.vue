<template>
  <g class="bascketballTeam" v-for="(player, index) in players" :key="index">
    <circle :cx="20 * index + 10" cy="10" r="10" />
  </g>
</template>

<script lang="ts">
import { defineComponent, ref, computed } from 'vue';

export default defineComponent({
    name: 'BascketballTeam',
    props: {
        message: {
            type: String,
            required: true,
        },
    },

    setup() {
        return {
            testData: 'test',
            players: [1, 2, 3, 4, 5],
        };
    },
});
</script>
