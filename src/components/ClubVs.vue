<script>
export default {
    name: 'ClubVs',
    props: ['club1', 'club2', 'data']
}
</script>

<template>

    <div class="container">
        <div class="clubs">
            <div class="club">
                <img :src="club1.logo" alt="">
                <h3>{{ club1.name }}</h3>
            </div>
            <div class="vs">VS</div>
            <div class="club">
                <h3>{{ club2.name }}</h3>
                <img :src="club2.logo" alt="">
            </div>
        </div>
        <div class="info">
            <div>
                <i class="fa-regular fa-calendar-days"></i>
                <strong>{{ data }}</strong>
            </div>
            <div>
                <i class="fa-solid fa-circle-plus"></i>
                <strong>Expert Stadium</strong>
            </div>

        </div>
    </div>


</template>

<style scoped>
.container {
    

    & .clubs {


        display: flex;
        align-items: center;
        justify-content: center;
        gap: 2rem;
        background-color: rgba(0, 0, 0, 0.334);

        & .club {
            display: flex;
            align-items: center;
            color: white;

        }

        & .vs {
            font-size: 5rem;
            font-weight: bold;
            color: white;

        }

    }

    & .info {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 2rem;
        margin: 0;
        padding: 0;
        background-color: rgba(0, 0, 0, 0.575);
        

        & div {
            display: flex;
            gap: 0.4rem;
            color: white;
            margin: 0;
            padding: 3px;

        }
    }
}
</style>