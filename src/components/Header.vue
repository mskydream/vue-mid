<template>
    <div>
        <v-navigation-drawer
        v-model="drawer"
        temporary
        right
        app
        >
            <v-list>
                <v-list-item
                    v-for="item in items"
                    :key="item.title"
                    :to="item.link"
                    link
                >
                    {{ item.title}}
                </v-list-item>
            </v-list>
        </v-navigation-drawer>
            <v-app-bar
            app
            flat 
            color="#fff"
            elevation="3"
            >
                <v-toolbar flat max-width="1080px" class="mx-auto">
                <v-toolbar-title>Photography</v-toolbar-title>

                    <v-spacer></v-spacer>

                <span class="hidden-sm-and-up">
                    <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
                </span>

                <v-toolbar-items class="hidden-xs-only">
                    <v-tabs
                        color="#212121"
                    >
                    <v-tab to="/">
                        Home
                    </v-tab>
                    <v-tab to="/about">
                        About
                    </v-tab>
                    <v-tab to="/contact">
                        Contact
                    </v-tab>
                    <v-tabs-slider color="#212121"></v-tabs-slider>
                    </v-tabs>
                </v-toolbar-items>
                </v-toolbar>
            </v-app-bar>
    </div>
</template>
<script>
export default {
    data(){
        return{
            drawer: false,
            items:[
                { title: 'Home', link:'/'},
                { title: 'About', link:'/about'},
                { title: 'Contact', link:'/contact'},
            ],
        }
    }
}
</script>