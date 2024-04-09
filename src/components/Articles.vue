<script>
export default {
    name: 'Articles',
    data () {
        return {
            articlesArray: [
                {
                    id: 1,
                    image: '/images/news1-1-300x300.png',
                    data: '29.05.2022 - Football',
                    title: 'What is Football?',
                    text: 'Football is a sport that is know as a ball game and is loved by [...]'
                },
                {
                    id: 2,
                    image: '/images/news2-1-300x300.png',
                    data: '29.05.2022 - Football',
                    title: 'Football Rules',
                    text: 'GOLDEN GOAL: In a football match, the goal scored by one of the teams in [...]'
                },
                {
                    id: 3,
                    image: '/images/news3-1-300x300.png',
                    data: '29.05.2022 - Football',
                    title: 'Football Features',
                    text: 'Football: It is an aerobic-based anaerobic sport in which jumps, kicks, turns, running with changing [...]'
                },
                {
                    id: 4,
                    image: '/images/news4-1-300x300.png',
                    data: '29.05.2022 - Football',
                    title: 'Football Terms',
                    text: 'GOLDEN GOAL: In a football match, the goal scored by one of the teams in [...]'
                },
    
            ]
        }
    }
}

</script>

<template>
    <div class="container">
        <div class="row">
            <div v-for="article in articlesArray" class="col">
                <div class="card">
                    <img :src="article.image" alt="">
                    <div>{{ article.data }}</div>
                    <h4 class="title">{{ article.title }}</h4>
                    <p>{{ article.text }}</p>
                    <button class="darkButton">More</button>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .container{
        width: 1408px;
        margin: auto;
        & .row {
            display: flex;
            justify-content: space-between;
            
            width: 100%;
            & .col {
                width: calc((100% / 4) - 20px);
                & .card {
                    display: flex;
                    flex-direction: column;
                    border-radius: 10px;
                    box-shadow: 10px 5px 5px rgba(0, 0, 0, 0.159);
                    padding: 3rem;
                    align-items: center;
                    > img {
                        width: 100%;
                    }
                    > .title {
                        font-size: 1.4rem;
                        font-weight: bold;
                        margin: 1rem 0;
                    }

                    > button {
                        margin-top: 1rem;
                        width: 60%;
                    }
                }
            }
        }
    }


</style>