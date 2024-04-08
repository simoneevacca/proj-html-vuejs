<script>
export default {
    name: 'ClubVs',
    props: ['club1', 'club2', 'data']
}
</script>

<template>

    <div class="clubs">
        <div class="club">
            <h3>{{ club1.name }}</h3>
            <img :src="club1.logo" alt="">
        </div>
        <div class="vs">VS</div>
        <div class="club">
            <img :src="club2.logo" alt="">
            <h3>{{ club2.name }}</h3>
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


</template>

<style>

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
        }</style>