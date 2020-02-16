<template>
    <v-container absolute style="padding-left: 70px;">
            <v-row>
            <v-col>
            <v-layout align-center column justify-center class="mt-5">
                    <h2 class=" font-weight mt-5 " style="font-size:35px;">Projects</h2>
                    <v-divider></v-divider>
                    <p class="font-weight-light ">Here are a few projects I have built recently. </p>
            </v-layout>
            <v-row>
                <v-col
                    v-for="project in projects"
                    :key="project.title"
                    @mouseover="project.hover = true"
                    @mouseleave="project.hover = false"
                    :class="{'hover': project.hover}"
                    cols="4"
                > 
                    <v-card outlined> 
                        <v-img
                        :src="project.image"
                        class="grey lighten-2"
                        >
                        <transition name="fade">
                            <v-overlay
                            v-if="project.hover"
                            absolute
                            opacity="0.8"
                            color="light-blue darken-4"
                            >
                            <!--Hover transitions-->
                            <v-container>
                                <v-layout fill-height>
                                    <v-flex xs12 align-end flexbox 
                                    >
                                        <v-btn class="ma-2" tile outlined color="orange darken-1"
                                        v-for="link in project.links"
                                        :key="link"
                                        :href="link.url"
                                        target="_blank"
                                        >                                        
                                            <v-icon>{{ link.mdi }}</v-icon>{{ link.media }}
                                        </v-btn>
                                    </v-flex>
                                </v-layout>
                            </v-container>
                            <div class="text-center">
                                <h2>{{ project.title }}</h2>
                                <p1>{{ project.description }}</p1>
                            </div>
                            <div>
                            <v-chip
                            v-for="tool in project.tools"
                            :key="tool.toolName"
                            class="ma-2"
                            v-bind:color="tool.color"
                            text-color="white"
                            ><v-icon>{{ tool.icon}}</v-icon>
                            {{ tool.toolName}}
                            </v-chip>
                            </div>
                            </v-overlay>
                        </transition>
                        </v-img>
                    </v-card>
                </v-col>
            </v-row>
            </v-col>
            </v-row>
    </v-container>
</template>

<script>
export default {
    name: 'Projects',
    data () {
        return {
            active: false,
            hoverBackground: require('../assets/blue.jpg'),
            projects: [
                {
                    title: 'Project Hub', 
                    image: require('../assets/react-redux.jpg'), 
                    description: 'A project dashboard React app with Redux & Firebase', 
                    links: [{media: "Github", mdi: "mdi-github-face"}, {mdi: "mdi-eye", url: "https://drive.google.com/file/d/1Rvna_HrmE9XUPJk0Ux1wwf_4ho0mq3xv/view?usp=sharing"}], 
                    tools: [{toolName: "React", icon: "mdi-react", color: "light-blue darken-1"}, {toolName: "Redux", icon: "mdi-electron-framework", color: "purple darken-1"}, {toolName: "Firebase", icon: "mdi-firebase", color: "amber darken-1"}]
                },
                {
                    title: 'Venues API (Front-end)', 
                    image: require('../assets/venues.jpg'), 
                    description: 'Full-stack project of a Venues website', 
                    links: [{media: "Github", mdi: "mdi-github-face", url: "https://github.com/ReiYoshi98/SENG365/tree/master/Travel-App-Frontend"}, {mdi: "mdi-eye", url: "https://drive.google.com/file/d/1uiLZl8zO_BAKVcbegPxvaGNWfqgaiotJ/view?usp=sharing"}], 
                    tools: [{toolName: "Vuejs", icon: "mdi-vuejs", color: "green darken-1"}, {toolName: "Nodejs", icon: "mdi-nodejs", color: "light-green darken-1"}]
                },
                {
                    title: 'My Portfolio website', 
                    image: require('../assets/portfolio.jpg'),
                    description: 'This current portfolio website', 
                    links: [{media: "Github", mdi: "mdi-github-face", url: "https://github.com/ReiYoshi98/My-Web-Portfolio"}], 
                    tools: [{toolName: "Vuejs", icon: "mdi-vuejs", color: "green darken-1"}, {toolName: "HTML", icon: "mdi-language-html5", color: "amber darken-1"}, {toolName: "CSS", icon: "mdi--language-css3", color: "light-blue darken-2"}]
                },
                {
                    title: 'Japan Day Brochure',
                    image: require('../assets/brochure.jpg'), 
                    description: 'A double sided A3 Brochure/Pamphlet designed for Japan Day 2019', 
                    links: [{media: "PDF", mdi:"mdi-file-pdf", url: "https://drive.google.com/file/d/1a1QBBsEvM8p_LlayLG3L1T9aOzJe-AuQ/view"}],
                    tools: [{toolName: "Ps", icon: "mdi-adobe", color: "light-blue darken-1"}, {toolName: "Ai", icon: "mdi-adobe", color: "amber darken-2"}, {toolName: "Id", icon: "mdi-adobe", color: "pink darken-1"}]
                },
                {
                    title: 'Heroes vs Villians', 
                    image: require('../assets/javagame.png'),
                    description: 'A game project which simulates a heroes vs villains theme using mini games', 
                    links: [{media: "Github", mdi: "mdi-github-face", url: "https://github.com/ReiYoshi98/SENG201"}, {mdi: "mdi-eye", url: "https://drive.google.com/file/d/1ahab5sOFirnqYkOAo-bnqwIUo9bb7muu/view?usp=sharing"}], 
                    tools: [{toolName: "Java", icon: "mdi-language-java", color: "red darken-1"}, {toolName: "Ai", icon: "mdi-adobe", color: "amber darken-2"}]
                },
                {
                    title: 'Flatting App', 
                    image: require('../assets/flatting image.jpg'),
                    description: 'Prototype for a mobile app with the scheme of assisting the house-sharing lifestyle', 
                    links: [{media: "Report", mdi: "mdi-file-pdf", url: "https://drive.google.com/file/d/18JGJ6FOXn6phA_eXPtQ3mgs_U6iBVEuY/view?usp=sharing"}], 
                    tools: [{toolName: "Xd", icon: "mdi-adobe", color: "purple darken-4"}]
                },
                {
                    title: 'Alien Invasion', 
                    image: require('../assets/alien invasion.png'),
                    description: 'An OpenGL program created with C++ language to display a live alien space scene', 
                    links: [{media: "Report", mdi: "mdi-file-pdf", url: "https://drive.google.com/file/d/1ow_cWQEtc7B1skxpkn2WzN_-ZGWHk7RQ/view?usp=sharing"}], 
                    tools: [{icon: "mdi-language-cpp", color: "cyan darken-1"}, {toolName: "OpenGl", color: "lime darken-1"}]
                },
                {
                    title: 'Ray Tracer', 
                    image: require('../assets/ray-tracer.jpg'),
                    description: 'Ray tracer implemented with the C++ language which can handle multiple object types with illumination features', 
                    links: [{media: "Report", mdi: "mdi-file-pdf", url: "https://drive.google.com/file/d/156ggTnH8wuNXfyq8yj9W8UqmUB3sgOyI/view?usp=sharing"}], 
                    tools: [{icon: "mdi-language-cpp", color: "cyan darken-1"}]
                }   
            ]
        }
    },
    created () {
        this.projects.forEach((project) => {
            this.$set(project, 'hover', false)
        })
    }
}
</script>

<style scoped>

.fade-enter-active {
  transition: opacity .5s
}

.fade-enter,
.fade-leave-active {
  opacity: 0
}

</style>