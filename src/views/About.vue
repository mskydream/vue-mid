<template>
    <div class="block">
        <v-container>
            <v-row dense>
                <v-col
                v-for="card in abouts"
                :key="card.title"
                :cols="card.flex"
                >
                <v-card tile>
                    <v-img
                    :src="card.src"
                    class="white--text align-end"
                    gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                    max-height="300px"
                    >
                    <v-card-title v-text="card.title"></v-card-title>
                    </v-img>
                </v-card>
                </v-col>
            </v-row>
            </v-container>


        <v-container>
            <p>
                Lorem ipsum dolor sit amet. Qui esse possimus non similique mollitia sed debitis Quis hic laudantium iste. Qui laboriosam expedita aut quae autem ut dolor officiis molestiae tempore. Et debitis distinctio rem porro reprehenderit et quod neque ex libero molestias sed harum deleniti. Ut harum esse qui nostrum facere et consequatur quas sed vero animi eos vero facilis et voluptas assumenda. Eos maxime nulla cum repellendus dolorem 33 quidem provident est tenetur cumque.
            </p>
        </v-container>

        <h1 class="text-center display-4 hidden-xs-only my-6">Our teams</h1>
        <h6 class="text-center title hidden-sm-and-up my-6">Our Teams</h6>
        
        <v-container>
            <v-row dense>
                <v-col
                v-for="person in team"
                :key="person.id"
                cols="12"
                sm="4"
                >
                <v-card shaped>
                    <v-img
                    :src="person.src"
                    class="white--text align-end"
                    gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                    max-height="300px"
                    >
                    <v-card-title v-text="person.name"></v-card-title>
                    <v-card-subtitle>{{person.proffesion}}</v-card-subtitle>
                    </v-img>
                </v-card>
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>
<script>
export default {
    data(){
        return{
            abouts: [
                { title: 'About Us', src: 'https://cdn.pixabay.com/photo/2021/12/03/21/22/kastoria-6843842_960_720.jpg', flex: 12 },
            ],
            team:[
                {
                    id:1,
                    name:'Peter Smith',
                    src:'https://cdn.pixabay.com/photo/2016/11/21/12/42/beard-1845166_960_720.jpg',
                    proffesion:'front-end',
                },
                {
                    id:2,
                    name:'Peter Smith',
                    src:'https://cdn.pixabay.com/photo/2017/08/01/12/14/wall-2564902_960_720.jpg',
                    proffesion:'ux/ui',
                },
                {
                    id:3,
                    name:'Peter Smith',
                    src:'https://cdn.pixabay.com/photo/2018/02/16/14/38/portrait-3157821_960_720.jpg',
                    proffesion:'back-end',
                },
            ]
        }
    }
    
}
</script>