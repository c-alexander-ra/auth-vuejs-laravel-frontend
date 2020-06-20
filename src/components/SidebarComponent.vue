<template>
<div v-if="authenticated">
    <v-navigation-drawer

        v-model="drawer"
        :mini-variant.sync="mini"
        permanent
        app
    >
        <v-list-item class="px-2 pb-2">
            <v-list-item-avatar>
                <v-img src="https://randomuser.me/api/portraits/men/85.jpg"></v-img>
            </v-list-item-avatar>

            <v-list-item-title>{{user.name}}</v-list-item-title>

            <v-btn
                icon
                @click.stop="mini= !mini"
            >
                <v-icon>keyboard_arrow_left</v-icon>
            </v-btn>
        </v-list-item>

        <v-divider></v-divider>

        <v-list dense >
            <v-list-item
                link
                :to="{name:'dashboard'}"
            >
                <v-list-item-icon>
                    <v-icon>dashboard</v-icon>
                </v-list-item-icon>

                <v-list-item-content>
                    <!--router-link :to="{name:'home'}">Home</router-link-->
                    <v-list-item-title >Dashboard</v-list-item-title>
                </v-list-item-content>
            </v-list-item>
        </v-list>
    </v-navigation-drawer>
</div>
</template>

<script>
    import {mapGetters} from 'vuex'

    export default {
        name: "SidebarComponent",
        data: () => ({
            drawer: true,
            items: [
                { title: 'Home', icon: 'dashboard' },
                { title: 'About', icon: 'question_answer' },
            ],
            mini:false,
            expandOnHover: true,
        }),
        computed:{
            ...mapGetters({
                authenticated: 'auth/authenticated',
                user: 'auth/user',

            })
        },
        methods:{
            alertar(o){
                console.log(o)
            }
        }

    }
</script>

<style scoped>

</style>