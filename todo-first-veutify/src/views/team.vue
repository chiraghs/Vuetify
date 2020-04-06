<template>
  <div class="home">
    <h1 class="subheading grey--text">Team</h1>

    <v-container class="my-4">
      <v-layout row wrap>
          <v-flex xs12 sm6 md4 lg3 v-for="person in Team" :key="person.name">
              <v-card flat class="text-center ma-3">
                  <v-responsive class="pt-4">
                    <v-avatar size=100>
                       <img :src="getImgLink(person.avatar)" :alt="person.name">
                    </v-avatar>
                  </v-responsive>

                  <v-card-text>
                      <div class="subheading">{{person.name}}</div>
                      <div class="grey--text">{{person.role}}</div>
                  </v-card-text>

                  <v-card-actions>
                      <v-btn depressed flat color="grey lighten-5">
                          <v-btn-icon > 
                              <v-icon small left color="grey" >message</v-icon>
                              <span class="grey--text text-lowercase">message</span>
                          </v-btn-icon>
                      </v-btn>
                  </v-card-actions>

              </v-card>
          </v-flex>
      </v-layout>

    </v-container>
  </div>
</template>

<script>


export default {
  data(){
      return{
          Team: [
        { name: 'Aang', role: 'Air', avatar:'avatar1.jpg' },
        { name: 'Zuko', role: 'Fire', avatar:'avatar2.jpg' },
        { name: 'Toph', role: 'Earth' , avatar:'avatar3.jpg'},
        { name: 'Sokka', role: 'Non-Bender', avatar:'avatar4.jpg' },
        { name: 'Katara', role: 'Water', avatar:'avatar5.jpg'},
        { name: 'Azula', role: 'Fire', avatar:'avatar6.jpg' },
        { name: 'Appa', role: 'Air', avatar:'avatar7.jpg' },
        { name: 'Momo', role: 'Air' , avatar:'avatar8.jpg'},
        { name: 'Suki', role: 'Non-Bender', avatar:'avatar9.jpg' },
        { name: 'Mai', role: 'Non-Bender', avatar:'avatar10.jpg'},
        { name: 'Tai Ly', role: 'Non-Bender', avatar:'avatar11.jpg'},
        { name: 'Jet', role: 'Fire', avatar:'avatar12.jpg'},
        { name: 'Jet', role: 'Non-Bender', avatar:'avatar13.jpg'},
      ]
      }
  },
  methods:{
      getImgLink(pic){
          return require('../assets/'+pic)
      }
  }
}
</script>
