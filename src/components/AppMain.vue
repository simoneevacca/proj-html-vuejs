<script>
import { state } from '../../state.js';
import ClubVs from './ClubVs.vue';
import Players from './Players.vue';
import LeagueTable from './LeagueTable.vue';


export default {
    name: 'AppMain',
    components: {
        ClubVs,
        Players,
        LeagueTable,
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



        <section class="upcoming-matchs">
            <div class="match-table">
                <h3>Upcoming Matchs</h3>

                <div>
                    <ClubVs :club1="state.schalke1" :club2="state.inter" data="October 20, 2022 17:00 pm" />
                    <ClubVs :club1="state.atletico" :club2="state.schalke2" data="October 20, 2022 17:00 pm" />
                    <ClubVs :club1="state.unitedFs" :club2="state.bayern" data="October 20, 2022 17:00 pm" />
                    <ClubVs :club1="state.arsenal" :club2="state.atletico" data="October 20, 2022 17:00 pm" />
                    <ClubVs :club1="state.istanbul" :club2="state.unitedFs" data="October 20, 2022 17:00 pm" />

                </div>
            </div>

        </section>



        <section class="players">
            <h3>Players</h3>
            <Players />
        </section>



        <section class="tables">
            <div class="container">

                <div class="league">
                    <h3>League Table</h3>
                    <table>
                        <tr class="dark">
                            <th class="team">TEAM</th>
                            <th>W</th>
                            <th>D</th>
                            <th>L</th>
                            <th>PTS</th>
                        </tr>
                        <LeagueTable :n="1" :logo="state.istanbul.logo" :name="state.istanbul.name" :w="18" :d="2" :l="0" :pts="42"/>
                        <LeagueTable :n="1" :logo="state.istanbul.logo" :name="state.istanbul.name" :w="18" :d="2" :l="0" :pts="42"/>
                        <LeagueTable :n="1" :logo="state.istanbul.logo" :name="state.istanbul.name" :w="18" :d="2" :l="0" :pts="42"/>
                        <LeagueTable :n="1" :logo="state.istanbul.logo" :name="state.istanbul.name" :w="18" :d="2" :l="0" :pts="42"/>
                        <LeagueTable :n="1" :logo="state.istanbul.logo" :name="state.istanbul.name" :w="18" :d="2" :l="0" :pts="42"/>
                        <LeagueTable :n="1" :logo="state.istanbul.logo" :name="state.istanbul.name" :w="18" :d="2" :l="0" :pts="42"/>
                        <LeagueTable :n="1" :logo="state.istanbul.logo" :name="state.istanbul.name" :w="18" :d="2" :l="0" :pts="42"/>
                        <LeagueTable :n="1" :logo="state.istanbul.logo" :name="state.istanbul.name" :w="18" :d="2" :l="0" :pts="42"/>
                        <LeagueTable :n="1" :logo="state.istanbul.logo" :name="state.istanbul.name" :w="18" :d="2" :l="0" :pts="42"/>

                    </table>

                </div>




                <div class="fixtures">
                    <h3>Fixtures & results</h3>
                </div>

            </div>
        </section>

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

                & img {
                    width: 150px;
                }

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

    & .upcoming-matchs {
        margin-top: 2rem;
        background-image: url("/images/saha.jpg");
        background-size: cover;

        & .match-table {
            width: 97%;
            padding-top: 2rem;
            display: flex;
            flex-direction: column;
            align-items: stretch;
            margin-top: 2rem;
            text-align: center;
            margin: auto;

            & h3 {
                color: white;
            }


            & div {
                margin-top: 1rem;

            }
        }
    }

    & .players {
        padding: 2rem 0;
        background-image: url("/images/player.jpg");
        background-size: cover;
        text-align: center;
        color: white;
    }

    & .tables {
        padding: 2rem 0;
        
        & .container {
            display: flex;
            width: 97%;
            margin: auto;
            
            & div {
                width: 50%;
                text-align: center;
            }
            
            & .league {
                table {
                    width: 100%;
                    border-collapse: collapse;

                    & .dark {
                        background-color: black;
                        color: white;
                        
                        & .team {
                            text-align: start;
                        }
                    }
                }
            }
        }
    }
}
</style>