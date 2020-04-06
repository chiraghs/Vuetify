<template>
    <nav>

    <v-toolbar flat class="grey lighten-3" >
      <v-app-bar-nav-icon class="grey--text"></v-app-bar-nav-icon>

      <v-toolbar-title  class="grey--text">ToDOChiz</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon v-model="drawer" @click="drawer =!drawer">
        <v-icon class="grey--text">mdi-dots-vertical</v-icon>
      </v-btn>
    </v-toolbar>



      <v-navigation-drawer app temporary
      class="px-0"
        v-model="drawer"
        :color="color"
        :expand-on-hover="expandOnHover"
        :mini-variant="miniVariant"
        :right="right"
        :src="bg"
        
        dark
      >
        <v-list
          dense
          nav
          class="py-0 px-1"
        >
          <v-list-item two-line :class="miniVariant && 'px-0'">
            <v-list-item-avatar size="70" class="mr-3">
              <img src="../assets/Chiragn.png">
            </v-list-item-avatar>

            <v-list-item-content>
              <v-list-item-title>Chirag</v-list-item-title>
              <v-list-item-subtitle>Developer</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>

          <v-divider></v-divider>

          <v-list-item
            v-for="item in links"
            :key="item.title"
            link router :to="item.route" class="py-1"
          >
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title>{{ item.text }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
      


       </nav>
</template>

<script>

export default {
    data(){
        return{
            drawer:false,
            links:[
                     { icon: 'dashboard', text: 'Dashboard', route: '/' },
                     { icon: 'folder', text: 'My Projects', route: '/projects' },
                     { icon: 'person', text: 'Team', route: '/team' },
                       
            ],
        right: true,
        miniVariant: false,
        expandOnHover: true,
        background: false,
      }
        },
    computed: {
      bg () {
        return this.background ? 'https://cdn.vuetifyjs.com/images/backgrounds/bg-2.jpg' : undefined
      },
    },
    
}
</script>