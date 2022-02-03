<template>
    <div>
        <h2 class="text-center display-4 hidden-xs-only my-9">The best cities for traveling</h2>
        <h6 class="text-center title hidden-sm-and-up my-9">The best cities for traveling</h6>

        <v-container class="my-5">
            <v-layout row wrap>
                <v-flex xs12 sm6 md4 lg3 v-for="(card,index) in cards" :key="index">
                    <v-card
                        class="ma-2 "
                        max-width="500px"
                    >
                        <v-img
                        class="text-right"
                        :src="card.src"
                        height="300px"
                        
                        >
                            <v-btn
                            
                            icon
                            dark
                            @click="card.like = !card.like"
                            >
                            <v-icon>
                                {{ card.like ? 'mdi-heart' : 'mdi-heart-outline' }}
                            </v-icon>
                            </v-btn>
                        </v-img>

                        <v-card-title>
                        {{card.title}}
                        </v-card-title>

                        <v-card-subtitle>
                        {{card.subtitle}}
                        </v-card-subtitle>

                        <v-card-actions>
                        <v-btn
                            color="indigo darken-1"
                            text
                        >
                            More
                        </v-btn>

                        <v-spacer></v-spacer>

                        <v-btn
                            color="indigo darken-1"
                            icon
                            @click="card.show = !card.show"
                        >
                            <v-icon>{{ card.show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
                        </v-btn>
                        </v-card-actions>

                        <v-expand-transition>
                        <div v-show="card.show">
                            <v-divider></v-divider>

                            <v-card-text>
                            {{card.text}}
                            </v-card-text>
                        </div>
                        </v-expand-transition>
                    </v-card>
                </v-flex>
            </v-layout>
        </v-container>
    </div>
</template>
<script>
  export default {
        data(){
            return{
                show: false,
                cards:[
                    {
                        title:'Paris',
                        subtitle:'Capital of France',
                        src:'https://research.euro.savills.co.uk/_images/paris-intro-2020.jpg',
                        text:"Also known as the Latin Quarter, the 5th arrondissement is home to the Sorbonne university and student-filled cafes. It's also known for its bookshops, including the famed Shakespeare & Company. Family-friendly attractions include the Jardin des Plantes botanical gardens and the National Museum of Natural History.",
                        show: false,
                        like: false,
                    },
                    {
                        title:'Dubai',
                        subtitle:'City in the United Arab Emirates',
                        src:'https://www.costacruises.eu/content/dam/costa/inventory-assets/ports/DXB/dubai.jpg.image.1125.1446.low.jpg',
                        text:"Dubai is a city and emirate in the United Arab Emirates known for luxury shopping, ultramodern architecture and a lively nightlife scene. Burj Khalifa, an 830m-tall tower, dominates the skyscraper-filled skyline. At its foot lies Dubai Fountain, with jets and lights choreographed to music. On artificial islands just offshore is Atlantis, The Palm, a resort with water and marine-animal parks.",
                        show: false,
                        like: false,
                    },
                    {
                        title:'Ankara',
                        subtitle:'Capital of Turkey',
                        src:'https://ankara.su/wp-content/uploads/2018/09/de3d9b3d91424b959daa0a5a910abca7.max-1200x800-1.jpg',
                        text:"Ankara, Turkey’s cosmopolitan capital, sits in the country’s central Anatolia region. It’s a center for the performing arts, home to the State Opera and Ballet, the Presidential Symphony Orchestra and several national theater companies. Overlooking the city is Anitkabir, the enormous hilltop mausoleum of Kemal Atatürk, modern Turkey’s first president, who declared Ankara the capital in 1923. ",
                        show: false,
                        like: false,
                    },
                    {
                        title:'New York',
                        subtitle:'City in New York State',
                        src:'https://www.buro247.ua/thumb/670x830_0/images/2018/01/800-statue-liberty-closed.jpg',
                        text:"There are so many elements that make New York City one of the best cities in the world. The city and the Statue of Liberty that travelers see as they arrive is symbolic of the culture and freedom that America stands for. The Big Apple is the financial hub of the United States, with Wall Street and international businesses.",
                        show: false,
                        like: false,
                    },
                    {
                        title:'London',
                        subtitle:'Capital of England',
                        src:'https://shershegoes.com/wp-content/uploads/London-Itinerary-for-First-Time-Visitors.jpg',
                        text:"London, the capital of England and the United Kingdom, is a 21st-century city with history stretching back to Roman times. At its centre stand the imposing Houses of Parliament, the iconic ‘Big Ben’ clock tower and Westminster Abbey, site of British monarch coronations. Across the Thames River, the London Eye observation wheel provides panoramic views of the South Bank cultural complex, and the entire city. ",
                        show: false,
                        like: false,
                    },
                    {
                        title:'Singapore',
                        subtitle:'Country in Asia',
                        src:'https://i.natgeofe.com/n/d3eb75f2-1cfb-4934-8def-8ff7a39985b8/1-urban-innovator-singapore-AP_17028110123351_3x4.jpg',
                        text:"Modern Singapore was founded in 1819 by Sir Stamford Raffles as a trading post of the British Empire. In 1867, the colonies in Southeast Asia were reorganised and Singapore came under the direct control of Britain as part of the Straits Settlements. During the Second World War, Singapore was occupied by Japan in 1942, and returned to British control as a separate crown colony following Japan's surrender in 1945. Singapore gained self-governance in 1959 and in 1963 became part of the new federation of Malaysia, alongside Malaya, North Borneo, and Sarawak. Ideological differences led to Singapore being expelled from the federation two years later and it became an independent country.",
                        show: false,
                        like: false,
                    },
                    {
                        title:'Rome',
                        subtitle:'Capital of Italy',
                        src:'https://travel.mqcdn.com/mapquest/travel/wp-content/uploads/2020/10/Trevi-Fountain.jpg',
                        text:"Rome is the capital city of Italy. It is also the capital of the Lazio region, the centre of the Metropolitan City of Rome, and a special comune named Comune di Roma Capitale.",
                        show: false,
                        like: false,
                    },
                    {
                        title:'Delhi',
                        subtitle:'City in India',
                        src:'https://images.unsplash.com/photo-1575566668200-7dcaa7b2cf28?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwcm9maWxlLXBhZ2V8OXx8fGVufDB8fHx8&w=1000&q=80',
                        text:"Delhi, India’s capital territory, is a massive metropolitan area in the country’s north. In Old Delhi, a neighborhood dating to the 1600s, stands the imposing Mughal-era Red Fort, a symbol of India, and the sprawling Jama Masjid mosque, whose courtyard accommodates 25,000 people. Nearby is Chandni Chowk, a vibrant bazaar filled with food carts, sweets shops and spice stalls.",
                        show: false,
                        like: false,
                    },
                    
                ]
            }
        }
  }
</script>