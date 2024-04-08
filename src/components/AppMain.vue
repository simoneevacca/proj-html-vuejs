<script>
import { state } from '../../state.js';
import ClubVs from './ClubVs.vue';

export default {
    name: 'AppMain',
    components: {
        ClubVs
    },

    data() {
        return {

            state,
        }
    },
    mounted() {
        // console.log(state.clubArray.istanbul);
    },

}
</script>

<template>
    <main>
    
        <section class="first-match">
            <div class="clubs">
                <div class="club">
                    <h3>{{ state.istanbul.name }}</h3>
                    <img :src="state.istanbul.logo" alt="">
                </div>
                <div class="vs">VS</div>
                <div class="club">
                    <img :src="state.unitedFs.logo" alt="">
                    <h3>{{ state.unitedFs.name }}</h3>
                </div>
            </div>
            <div class="info">
                <div>
                    <i class="fa-regular fa-calendar-days"></i>
                    <strong>May 21, 2022 18:05 pm</strong>
                </div>
                <div>
                    <i class="fa-solid fa-circle-plus"></i>
                    <strong>Expert Stadium</strong>
                </div>

            </div>
            <div class="darkButton">View Match Details</div>
        </section>


        <ClubVs :club1="state.schalke1" :club2="state.inter" />
    </main>

</template>

<style>
main {
    & .first-match {
        margin-top: 2rem;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;

        & .clubs {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 2rem;

            & .club {
                display: flex;
                align-items: center;

            }

            & .vs {
                font-size: 5rem;
                font-weight: bold;
            }

        }

        & .info {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 1.5rem;

            & div {
                display: flex;
                gap: 0.4rem;
            }
        }

        & .darkButton {
            width: 200px;
        }


    }
}
</style>