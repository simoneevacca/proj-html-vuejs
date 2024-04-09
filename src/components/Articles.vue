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
                    text: 'Football is a sport that is know as a baòò game and is loved by [...]'
                },
                {
                    id: 2,
                    image: '/images/news2-1-300x300.png',
                    data: '29.05.2022 - Football',
                    title: 'What is Football?',
                    text: 'Football is a sport that is know as a baòò game and is loved by [...]'
                },
                {
                    id: 3,
                    image: '/images/news3-1-300x300.png',
                    data: '29.05.2022 - Football',
                    title: 'What is Football?',
                    text: 'Football is a sport that is know as a baòò game and is loved by [...]'
                },
                {
                    id: 4,
                    image: '/images/news4-1-300x300.png',
                    data: '29.05.2022 - Football',
                    title: 'What is Football?',
                    text: 'Football is a sport that is know as a baòò game and is loved by [...]'
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
                    <div>{{ article.title }}</div>
                    <p>{{ article.text }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
    .container{
        width: 1408px;
        margin: auto;
        & .row {
            display: flex;
            gap: 1rem;
            & .col {

                & .card {
                    border: 1px solid black;
                    display: flex;
                    flex-direction: column;
                }
            }
        }
    }


</style>