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
                <v-form @submit.prevent="login">
                <v-card-text>
                        <v-text-field
                            v-model="user.name"
                            label="Name"
                            required
                        ></v-text-field>

                        <v-text-field
                            v-model="user.email"
                            label="E-mail"
                            required
                        ></v-text-field>

                        <v-text-field
                            v-model="user.password"
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
    export default {
        name: "SignIn",
        data: () => ({
            user:{
                name: '',
                email: '',
                password: ''
            }
        }),

        methods: {

            login(){
                console.log('log')
            }
        },
    }
</script>

<style scoped>

</style>