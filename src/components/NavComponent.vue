<template>
    <v-app-bar
        app
        color="white"
    >
        <v-app-bar-nav-icon></v-app-bar-nav-icon>

        <v-toolbar-title>Title</v-toolbar-title>

        <v-spacer></v-spacer>

        <v-tooltip left>
            <template v-slot:activator="{ on, attrs }">
                <v-btn icon v-bind="attrs" v-on="on" :to="{name:'signin'}">
                    <v-icon>power</v-icon>
                </v-btn>
            </template>
            <span>Sig In</span>
        </v-tooltip>
        <v-tooltip left>
            <template v-slot:activator="{ on, attrs }">
                <v-btn icon v-bind="attrs" v-on="on">
                    <v-icon>settings_power</v-icon>
                </v-btn>
            </template>
            <span>Sing Out</span>
        </v-tooltip>
    </v-app-bar>
</template>

<script>
    export default {
        name: "NavComponent"
    }
</script>

<style scoped>

</style>