<script>
export default {
    name: 'Players',

    data() {
        return {
            playersArray: [
                {
                    id: 1,
                    image: '/images/player1.jpg',
                    number: '07',
                    name: 'Adam Brown',
                    role: 'Forwarder'
                },
                {
                    id: 2,
                    image: '/images/player2.jpg',
                    number: '09',
                    name: 'Michael Kayn',
                    role: 'Forwarder'
                },
                {
                    id: 3,
                    image: '/images/player3.jpg',
                    number: '11',
                    name: 'Michael Lee',
                    role: 'Forwarder'
                },
                {
                    id: 4,
                    image: '/images/player4.jpg',
                    number: '15',
                    name: 'Ethan Smith',
                    role: 'Forwarder'
                },
                {
                    id: 5,
                    image: '/images/player5.jpg',
                    number: '20',
                    name: 'Brian Hooks',
                    role: 'Forwarder'
                },
                {
                    id: 6,
                    image: '/images/player6.jpg',
                    number: '18',
                    name: 'Stan Jackson',
                    role: 'Forwarder'
                },
            ],
            viewAll: false,
            button: 'View All Players'
        }

    },
    methods: {
        showAll() {
            this.viewAll = !this.viewAll
            if (this.button == 'View All Players') {
                this.button = 'Hide Players'

            } else if (this.button == 'Hide Players') {
                this.button = 'View All Players'

            }

            console.log(this.viewAll);
        }
    }
}
</script>

<template>

    <div class="container">

        <div class="row" v-if="viewAll=== false">
            <div class="col" v-for="index in 4" :key="index">
                <div class="card">
                    <img :src="playersArray[index - 1].image" alt="">
                    <div class="text">
                        <div class="number">{{ playersArray[index - 1].number }}</div>
                        <div>{{ playersArray[index - 1].name }} - {{ playersArray[index - 1].role }}</div>
                    </div>
                </div>
            </div>
        </div>



        <div class="row" v-else-if="viewAll === true">
            <div class="col" v-for="player in playersArray">
                <div class="card">
                    <img :src="player.image" alt="">
                    <div class="text">
                        <div class="number">{{ player.number }}</div>
                        <div>{{ player.name }} - {{ player.role }}</div>
                    </div>
                </div>

            </div>
        </div>
        
        <button class="darkButton" @click="showAll()">{{ button }}</button>


    </div>


</template>

<style scoped>
.container {
    max-width: 95%;
    margin: auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    

    & .row {
        display: flex;
        flex-wrap: wrap;



        & .col {
            width: calc((100% / 12) * 3);
            padding: 2rem;

            & .card {
                position: relative;

                & img {
                    width: 100%;
                    border-radius: 50px;


                }

                & .text {
                    position: absolute;
                    bottom: 0px;
                    z-index: 1;
                    background-color: black;
                    color: white;
                    width: 100%;
                    border-radius: 30px;
                    height: 25%;
                    display: flex;
                    flex-direction: column;
                    justify-content: center;
                    align-items: center;

                    & .number {
                        font-size: 2rem;
                        font-weight: bold
                    }
                }

            }

        }
    }
    & button {
        width: 200px;
        border: 1px solid white;
    }
}
</style>