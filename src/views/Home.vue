<template>
    <v-container>
            <v-carousel height="auto" hide-delimiters>
                <v-carousel-item
                v-for="(item,i) in items"
                :key="i"
                :src="item.src"
                aspect-ratio="1.77"
                ></v-carousel-item>
            </v-carousel>
        <Travel></Travel>
    </v-container>
</template>
<script>
import Travel from '../components/Travel.vue'
export default {
    components:{
        Travel
    },
    data () {
        return {
        items: [
            {
            src: 'https://cdn.pixabay.com/photo/2021/06/18/06/51/seagull-6345331_960_720.jpg',
            },
            {
            src: 'https://cdn.pixabay.com/photo/2020/04/13/09/07/city-5037397_960_720.jpg',
            },
            {
            src: 'https://cdn.pixabay.com/photo/2022/01/18/16/49/town-6947538_960_720.jpg',
            },
            {
            src: 'https://cdn.pixabay.com/photo/2022/01/16/13/25/cityscape-6942013_960_720.jpg',
            },
        ],
        }
    },
}
</script>