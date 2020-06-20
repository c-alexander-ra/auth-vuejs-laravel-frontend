<template>
<div>
    <v-row>
        <v-col :cols="6" class="mx-auto">
            <v-card class="pa-5">
                <v-card-title>
                    <v-row justify="center">
                        <h3 >Login</h3>
                    </v-row>
                </v-card-title>
                <v-form @submit.prevent="submit">
                <v-card-text>
                        <!--v-text-field
                            v-model="form.name"
                            label="Name"
                            required
                        ></v-text-field-->

                        <v-text-field
                            v-model="form.email"
                            label="E-mail"
                            required
                        ></v-text-field>

                        <v-text-field
                            v-model="form.password"
                            label="Password"
                            required
                            type="password"
                        ></v-text-field>

                </v-card-text>
                <v-card-actions >
                    <v-btn block
                           color="success"
                           class="mr-4"
                           type="submit"
                    >
                        Sign In
                    </v-btn>
                </v-card-actions>
                </v-form>
            </v-card>
        </v-col>
    </v-row>
</div>
</template>

<script>

    //import axios from 'axios';

    import  {mapActions} from 'vuex';

    export default {
        name: "SignIn",
        data: () => ({
            form:{
              //  name: '',
                email: '',
                password: ''
            }
        }),

        methods: {
            ...mapActions({
                signIn:'auth/signIn'
            }),
            submit(){
                this.signIn(this.form)
                    .then(()=>{
                        this.$router.replace({
                            name:'dashboard'
                        })
                    })
                    .catch(()=>{
                        console.log('failed')
                    })
                /*let response = await axios.post('auth/signin', this.form);
                console.log(response.data)*/
            }
        },
    }
</script>

<style scoped>

</style>