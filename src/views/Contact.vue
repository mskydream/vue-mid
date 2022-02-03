<template>
    <div>
        <v-container>
            <v-row dense>
                <v-col
                v-for="contact in contacts"
                :key="contact.title"
                :cols="contact.flex"
                >
                <v-card tile>
                    <v-img
                    :src="contact.src"
                    class="white--text align-end"
                    gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                    max-height="300px"
                    >
                    <v-card-title v-text="contact.title"></v-card-title>
                    </v-img>
                </v-card>
                </v-col>
            </v-row>
        </v-container>

        <h1 class="text-center display-4 hidden-xs-only my-6">Your review</h1>
        <h6 class="text-center title hidden-sm-and-up my-6">Your review</h6>

        <div max-width="1080px" class="pa-6">
            <v-form
                
                ref="form"
                v-model="valid"
                lazy-validation
            >
                <v-text-field
                v-model="name"
                :counter="10"
                :rules="nameRules"
                label="Name"
                required
                ></v-text-field>

                <v-text-field
                v-model="email"
                :rules="emailRules"
                label="E-mail"
                required
                ></v-text-field>

                <v-textarea
                v-model="message"
                :rules="messageRules"
                label="Message"
                required
                ></v-textarea>


                <v-btn
                :disabled="!valid"
                color="success"
                class="mr-4"
                @click="validate"
                >
                Submit
                </v-btn>

                <v-btn
                color="error"
                class="mr-4"
                @click="reset"
                >
                Reset 
                </v-btn>

            </v-form>
        </div>

        
       
    </div>
</template>
<script>
export default {
    data(){
        return{
            contacts: [
                { title: 'About Us', src: 'https://cdn.pixabay.com/photo/2022/01/07/07/13/chicago-6921297_960_720.jpg', flex: 12 },
            ],
            valid: true,
            name: '',
            nameRules: [
                v => !!v || 'Name is required',
                v => (v && v.length <= 10) || 'Name must be less than 10 characters',
            ],
            email: '',
            emailRules: [
                v => !!v || 'E-mail is required',
                v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
            ],
            message: '',
            messageRules: [
                v => !!v || 'Message is required',
                v => (v && v.length >= 10) || 'Message must be more than 10 characters',
            ],
        }
    },
    methods: {
      validate () {
        this.$refs.form.validate()
      },
      reset () {
        this.$refs.form.reset()
      },
    },
}
</script>