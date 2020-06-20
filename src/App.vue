<template>
    <v-app>
        <NavComponent/>
        <SidebarComponent/>
        <v-main>
            <v-container>
                <router-view></router-view>
            </v-container>
        </v-main>
    </v-app>
</template>

<script>

    import NavComponent from "@/components/NavComponent";
    import SidebarComponent from "@/components/SidebarComponent";

    export default {
        name: 'App',

        components: {
            NavComponent,
            SidebarComponent
        },

        data: () => ({
            //
        }),
    };
</script>
