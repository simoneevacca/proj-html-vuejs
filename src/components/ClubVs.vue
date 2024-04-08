<script>
    export default {
        name: 'ClubVs',
        props: ['club1', 'club2']
    }
</script>

<template>

    
    <img :src="club1.logo" alt="">
    <div>VS</div>
    <img :src="club2.logo" alt="">


</template>

<style>
</style>