<script>
export default {
    name: 'Fixtures',
    props: ['club1', 'club2']
}
</script>

<template>
    <div class="container">
        <div class="clubs">
            <div class="club">
                <img :src="club1.logo" alt="">
                <div>{{ club1.name }}</div>
            </div>
            <div class="vs"><strong>VS</strong></div>
            <div class="club">
                <div>{{ club2.name }}</div>
                <img :src="club2.logo" alt="">
            </div>
        </div>
    </div>

</template>

<style scoped>
    .container {
       
        
       & .clubs {
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 2rem;
        & .club {
            display: flex;
            align-items: center;
            & img {
            width: 60px;

            }
        }
       }
    }
</style>