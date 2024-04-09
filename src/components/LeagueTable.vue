<script>
import { state } from '../../state.js';

export default {
    name: 'LeagueTable',
    props: {
        n: Number,
        logo: String,
        name: String,
        w: Number,
        d: Number,
        l: Number,
        pts: Number
    },
    data() {
        return {

            state,
        }
    },
}
</script>

<template>


    <tr>
        <td class="team">
            {{n}}
            <img :src="logo" alt="">
            {{ name }}
        </td>
        <td>{{ w }}</td>
        <td>{{ d }}</td>
        <td>{{ l }}</td>
        <td><strong>{{ pts }}</strong></td>
    </tr>




</template>

<style scoped>
table {
    width: 100%;
}
& tr {
    background-color: #f3f3f3;
    .team {
        display: flex;
        align-items: center;
        justify-content: flex-start;
        padding-left: 0.8rem;
    
        & img {
            width: 60px;
        }
    
    }
}


</style>