<script>
export default {
    name: 'Articles',
    data() {
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

            ],

            pageId: null
        }
    },

    methods: {
        pageIndex(id) {
            this.pageId = id;
            console.log(this.pageId);
        }
    }
}

</script>

<template>
    <div class="container">

        <div class="ico">
            <i class="fa-regular fa-thumbs-up"></i>
        </div>
        <div>
            <h3>Resent New & Articles</h3>
            <p>Be aware of the football world.</p>
        </div>

        <div class="row">
            <div v-for="article in articlesArray" class="col">
                <div class="card" @mouseenter="pageIndex(article.id)" :class="{'card-selected' : pageId == article.id}">
                    <img :src="article.image" alt="">
                    <div>{{ article.data }}</div>
                    <h4 class="title">{{ article.title }}</h4>
                    <p>{{ article.text }}</p>
                    <button class="darkButton">More</button>
                </div>
            </div>
        </div>

        <div class="page">
            <div class="page-id" :class="{'page-selected' : pageId == 1}"></div>
            <div class="page-id" :class="{'page-selected' : pageId == 2}"></div>
            <div class="page-id" :class="{'page-selected' : pageId == 3}"></div>
            <div class="page-id" :class="{'page-selected' : pageId == 4}"></div>
        </div>
    </div>
</template>

<style scoped>
.container {
    padding: 8rem 0 4rem 0;
    width: 1408px;
    margin: auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
    text-align: center;

    & .ico {
        width: 170px;
        aspect-ratio: 1;
        border-radius: 50%;
        background-color: black;
        display: flex;
        justify-content: center;
        align-items: center;

        & .fa-thumbs-up {
            color: white;
            font-size: 3rem;
            border: 5px solid white;
            border-radius: 50%;
            padding: 1.5rem;
        }

    }

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
                transition: 1s;

                >img {
                    width: 100%;
                }

                >.title {
                    font-size: 1.4rem;
                    font-weight: bold;
                    margin: 1rem 0;
                }

                >button {
                    margin-top: 1rem;
                    width: 60%;
                }
            }

            & .card-selected {
                padding: 1rem;

            }
        }
    }

    & .page {
        margin-top: 3rem;
        display: flex;
        gap: 0.5rem;
        & .page-id {
            width: 45px;
            height: 10px;
            background-color: rgb(162, 162, 162);
            border-radius: 15px;
            transition: 1s;
        }
        & .page-selected {
            width: 120px;
            height: 10px;
            background-color: black;
        }

    }
}
</style>