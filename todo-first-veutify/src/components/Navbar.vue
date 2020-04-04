<template>
    <nav>
        <v-toolbar flat app>
        <v-app-bar-nav-icon class="grey--text" @click="drawer =! drawer"></v-app-bar-nav-icon>
          <v-toolbar-title class="text-upper grey--text">
              <span class="font-weight-light">Todo</span>
              <span>Chiz</span>
          </v-toolbar-title>
          <v-spacer></v-spacer>
          <v-btn text color="grey">
              <span>Sign Out</span>
              <v-icon right>mdi-exit-to-app</v-icon>
          </v-btn>
        </v-toolbar >


        <v-navigation-drawer temporary app class="teal" v-model="drawer">
           
      <v-list>
       <v-list-item-group v-model="item" color="primary">
        <v-list-item
          v-for="(link, i) in links"
          :key="i" route :to="link.route"
        >
          <v-list-item-icon>
            <v-icon class="white--text">{{link.icon}}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title class="white--text" v-text="link.text"></v-list-item-title>
          </v-list-item-content>
        </v-list-item>
       </v-list-item-group> 
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
                       
            ]
        }
    }
    
}
</script>