<template>
  <svg class="hall" text-anchor="middle" viewBox="0 0 1500 1100">
        <pattern id="img-ball-c" width="100%" height="100%" viewBox="0 0 100 100">
            <circle fill="#ff5a00" r="100" cx="50" cy="50" />
            <path
                stroke="#000"
                stroke-width="2"
                fill="none"
                d="m14.6 85.3l70.7-70.8M50 0s-35.4 85.3 50
                  50M14.6 14.6s17.7 52.7 70.7 70.7M0 50s50 0 50 50"
            />
        </pattern>
        <g id="court">
            <rect x="0" y="0" width="100%" height="1000" />
            <path
                d="M90 300c170 710 1150 710 1320 0M570
                  580c10 240 350 240 360 0M625 157.5c5 167.5 245 167.5 250 0"
                fill="none"
                stroke="#000"
            />
            <path d="M660 120h180m-90 0v15M90 0v300M1410 0v300" fill="none" stroke="#000" />
            <path d="M505 0v580h490V0" fill="none" stroke="#000" />
            <circle r="22.5" cx="750" cy="157.5" fill="none" stroke="#000" />
        </g>
        <rect id="bench" x="0" y="1000" width="100%" height="100" />
        <BascketballTeam></BascketballTeam>
    </svg>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import BascketballTeam from './BascketballTeam.vue';

@Options({
    components: {
        BascketballTeam,
    },
    props: {
        msg: String,
    },
})
export default class BasketballHalfPlayground extends Vue {
    msg!: string
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
#constructor {
    .draggable {
        cursor: move;
    }
}

#court,
#bench {
    fill: none;
    stroke: #000;
    stroke-width: 1;
}

.ball {
    stroke-width: 0;
}

.player {
    fill: #ffc107;
    stroke: #4caf50;
    stroke-width: 6px;

    text {
        font-size: 30px;

        fill: #000;
        stroke: none;
    }

    &.active {
        opacity: .5;
    }

    &.with-ball {
        stroke: #ff6f00;
    }
}

svg.hall {
    display: block;

    max-height: 70vh;
    margin: auto;

    &.ball {
        .fantom-ball {
            opacity: 1;
        }

        .arrow-ball {
            opacity: .9;
        }
    }
    @for $i from 1 through 5 {
        &.player-#{$i} {
            .fantom-player-#{$i} {
                opacity: 1;
            }

            .arrow-player-#{$i} {
                opacity: .8;
            }
        }
    }
}

.fantom {
    opacity: .5;

    fill: #fff;
    stroke: #4caf50;
    stroke-width: 4px;

    text {
        font-size: 25px;

        fill: #000;
        stroke: none;
    }

    &.with-ball {
        fill: #ff6f00;
    }

    &.fantom-ball {
        fill: #ff6f00;
        stroke: #ff6f00;
        stroke-width: 0;
    }
}

.line,
.arrow {
    opacity: .2;

    stroke: #000;
    stroke-width: 6px;

    &.with-ball {
        fill: #ff6f00;
        stroke: #ff6f00;
    }

    &.arrow-ball {
        fill: #ff6f00;
        stroke: #ff6f00;
    }
}

.step-container {
    min-height: 40px;
}

</style>
