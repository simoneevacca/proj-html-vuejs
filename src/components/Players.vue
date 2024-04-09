<script>
export default {
    name: 'Players',

    data() {
        return {
            playersArray: [
                {
                    image: '/images/player1.jpg',
                    number: '07',
                    name: 'Adam Brown',
                    role: 'Forwarder'
                },
                {
                    image: '/images/player2.jpg',
                    number: '09',
                    name: 'Michael Kayn',
                    role: 'Forwarder'
                },
                {
                    image: '/images/player3.jpg',
                    number: '11',
                    name: 'Michael Lee',
                    role: 'Forwarder'
                },
                {
                    image: '/images/player4.jpg',
                    number: '15',
                    name: 'Ethan Smith',
                    role: 'Forwarder'
                },
                {
                    image: '/images/player5.jpg',
                    number: '20',
                    name: 'Brian Hooks',
                    role: 'Forwarder'
                },
                {
                    image: '/images/player6.jpg',
                    number: '18',
                    name: 'Stan Jackson',
                    role: 'Forwarder'
                },
            ]
        }
    }
}
</script>

<template>

    <div class="container" >
        <div class="row">
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

    </div>


</template>

<style scoped>
    .container {
        max-width: 95%;
        margin: auto;
        
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
    }
</style>