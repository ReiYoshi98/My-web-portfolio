<template>
      <v-container absolute grid-list-md fill-height>
        <v-spacer></v-spacer>
        <v-layout row wrap align-center>
            <v-flex>
              <p class="display-2">Rei Yoshinari</p>
              <p class="overline">Front End Development | UX/UI Design | Software Development</p>
              <v-btn :href="cvUrl" target="_blank">Download CV</v-btn>
              <v-btn :href="gitUrl" target="_blank" rounded><v-icon>mdi-github-face</v-icon></v-btn>
              <v-btn :href="linkdnUrl" target="_blank" rounded><v-icon>mdi-linkedin</v-icon></v-btn>
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
            gitUrl: "https://github.com/ReiYoshi98?tab=repositories",
            cvUrl: "https://drive.google.com/file/d/1_FSleEG_IXXKHKDkQSO90eQDojnjOSS6/view?usp=sharing",
            linkdnUrl: "https://www.linkedin.com/in/rei-yoshinari-249357138/"
        }
    }
}
</script>