<template>
      <v-container absolute grid-list-md fill-height>
        <v-spacer></v-spacer>
        <v-layout row wrap align-center>
            <v-flex>
              <p class="display-2">Rei Yoshinari</p>
              <p class="overline">Front End Development | UX/UI Design | Software Development</p>
              <v-btn>Contact me</v-btn>
              <v-btn>Download CV</v-btn>
              <v-btn rounded><v-icon>mdi-github-face</v-icon></v-btn>
              <v-btn rounded><v-icon>mdi-linkedin</v-icon></v-btn>
            </v-flex>
        </v-layout>
        <v-spacer></v-spacer>
      </v-container>
</template>

<script>
export default {
    name: 'Home',
    data () {
        return {
            msg: '',
            switch1: true
        }
    }
}
</script>