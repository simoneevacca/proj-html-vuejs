<script>
import { state } from '../../state.js';
import ClubVs from './ClubVs.vue';
import Players from './Players.vue';
import LeagueTable from './LeagueTable.vue';
import Fixtures from './Fixtures.vue';



export default {
    name: 'AppMain',
    components: {
        ClubVs,
        Players,
        LeagueTable,
        Fixtures,

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
                        <thead>
                            <tr class="dark">
                                <th class="team">TEAM</th>
                                <th>W</th>
                                <th>D</th>
                                <th>L</th>
                                <th>PTS</th>
                            </tr>
                        </thead>
                        <tbody>
                            <LeagueTable :n="1" :logo="state.istanbul.logo" :name="state.istanbul.name" :w="18" :d="2"
                                :l="0" :pts="42" />
                            <LeagueTable :n="2" :logo="state.unitedFs.logo" :name="state.unitedFs.name" :w="14" :d="2"
                                :l="1" :pts="35" />
                            <LeagueTable :n="3" :logo="state.schalke1.logo" :name="state.schalke1.name" :w="13" :d="3"
                                :l="0" :pts="32" />
                            <LeagueTable :n="4" :logo="state.inter.logo" :name="state.inter.name" :w="13" :d="2" :l="1"
                                :pts="31" />
                            <LeagueTable :n="5" :logo="state.madrid.logo" :name="state.madrid.name" :w="13" :d="1"
                                :l="2" :pts="30" />
                            <LeagueTable :n="6" :logo="state.schalke2.logo" :name="state.schalke2.name" :w="11" :d="0"
                                :l="3" :pts="28" />
                            <LeagueTable :n="7" :logo="state.arsenal.logo" :name="state.arsenal.name" :w="10" :d="5"
                                :l="0" :pts="26" />
                            <LeagueTable :n="8" :logo="state.bayern.logo" :name="state.bayern.name" :w="10" :d="2"
                                :l="2" :pts="24" />
                            <LeagueTable :n="9" :logo="state.atletico.logo" :name="state.atletico.name" :w="9" :d="0"
                                :l="4" :pts="20" />
                        </tbody>
                        <tfoot>
                            <tr>
                                <td colspan="5"><strong>View Full League Table</strong></td>
                            </tr>
                        </tfoot>
                    </table>

                </div>


                <div class="fixtures">
                    <h3>Fixtures & results</h3>
                    <div class="table">
                    <Fixtures class="lighter" :club1="state.istanbul" :club2="state.unitedFs"/>
                    <Fixtures class="light" :club1="state.istanbul" :club2="state.unitedFs"/>
                    <Fixtures class="lighter" :club1="state.istanbul" :club2="state.unitedFs"/>
                    <Fixtures class="light" :club1="state.istanbul" :club2="state.unitedFs"/>
                    <Fixtures class="lighter" :club1="state.istanbul" :club2="state.unitedFs"/>
                    <Fixtures class="light" :club1="state.istanbul" :club2="state.unitedFs"/>
                    <Fixtures class="lighter" :club1="state.istanbul" :club2="state.unitedFs"/>
                    <Fixtures class="light" :club1="state.istanbul" :club2="state.unitedFs"/>
                    <Fixtures class="lighter" :club1="state.istanbul" :club2="state.unitedFs"/>
                    <div class="foot"><strong>View Full Fixtures</strong></div>
                </div>


                </div>

            </div>
        </section>

        <section class="bet-divider">
            <img src="/images/reklam.jpg" alt="">
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
        padding-bottom: 3rem;
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
        padding: 3rem 0;
        & h3 {
            margin-bottom: 2rem;
        }
        & .container {
            display: flex;
            width: 97%;
            margin: auto;

            > div {
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
                            padding-left: 0.8rem;
                        }
                    }

                    & thead {
                        height: 2rem;

                    }

                    & tfoot {
                        background-color: black;
                        color: white;
                        height: 3rem;
                        display: flex;
                        align-items: center;
                        justify-content: center;
                        width: 100%;
                    }
                }
            }

            & .fixtures {
                & .table{
                height: 620px;

                & .light, .lighter, .foot {
                    height: calc(620px / 10);
                }
                
                & .light {
                    background-color: #ebebeb;
                }
                & .lighter {
                    background-color: #f3f3f3;
                }
                & .foot {
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    background-color: black;
                    color: white;
                    margin: 0 13.65px;
                    
                }
            }
            }


        }
    }

    & .bet-divider {
        text-align: center;
        width: 100%;
    }

    
}
</style>