<template>
    <v-navigation-drawer
        permanent
        expand-on-hover
        app
        mobile-break-point
    > 
    <v-img
    :src="image"
    height="100%"
    background-opacity="0.7"
    >
        <v-list>
            <v-list-item class="px-2">
                <v-icon large>mdi-arrow-right-box</v-icon>
              </v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list
            nav
            dense
            
        >
            <v-list-item link router to="/">
                <v-list-item-icon>
                    <v-icon>mdi-home</v-icon>
                </v-list-item-icon>
                <v-list-item-title>Home</v-list-item-title>
            </v-list-item>
            <v-list-item link router to="/projects">
                <v-list-item-icon>
                    <v-icon>mdi-hexagon-multiple</v-icon>
                </v-list-item-icon>
                <v-list-item-title>Projects</v-list-item-title>
            </v-list-item>
            <v-list-item link router to="/skills">
                <v-list-item-icon>
                    <v-icon>mdi-tools</v-icon>
                </v-list-item-icon>
                <v-list-item-title>Skills</v-list-item-title>
            </v-list-item>
        </v-list>
    </v-img>
    </v-navigation-drawer>
</template>

<script>

export default {
    name: 'navbar',
    data () {
        return {
            image: require('../assets/white-and-blue.png')
        }
    }
}
</script>