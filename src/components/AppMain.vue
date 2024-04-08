<script>
    import { state } from '../../state.js';
    import ClubVs from './ClubVs.vue';

    export default {
        name: 'AppMain',
        components: {
            ClubVs
        },
        
        data (){
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

    <ClubVs :club1="state.schalke1" :club2="state.inter"/>
    

</template>

<style>

</style>