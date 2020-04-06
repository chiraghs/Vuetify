<template>
  <div class="dashboard">
    <h4 class=" grey--text ligten-2 mx-4">Dashboard</h4>

    <v-container class="my-4"  >

      <v-layout row class="mb-3">

        <v-tooltip top>
        <template class="small" v-slot:activator="{ on }">
           <v-btn small flat color="grey lighten-4" @click="sortBy('title')" v-on="on">
           <v-btn-icon >
              <v-icon left color="grey">folder</v-icon>
            </v-btn-icon>
          <span class="caption text-lowercase grey--text">By Project</span>
        </v-btn>
        </template>
        <span>Sort By Project Name</span>
        </v-tooltip>

        <v-tooltip top>
           <template class="small" v-slot:activator="{ on }">
        <v-btn small flat color="grey lighten-4 ml-5" @click="sortBy('person')" v-on="on">
           <v-btn-icon >
              <v-icon left color="grey">person</v-icon>
            </v-btn-icon>
          <span class="caption text-lowercase grey--text">By Person</span>
        </v-btn>
        </template>
        <span>Sort By Person Name</span>
        </v-tooltip>

      </v-layout>
      
      <v-card flat v-for="project in projects" :key="project.title">
        <v-layout row wrap :class="`pa-3 my-1 project ${project.status}`">
          <v-flex xs12 md6>
            <div class="caption grey--text">Project</div>
            <div>{{project.title}}</div>
          </v-flex>

          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Person</div>
            <div>{{project.person}}</div>
          </v-flex>

          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Due by</div>
            <div>{{project.due}}</div>
          </v-flex>

          <v-flex xs2 sm4 md2>
            <div class="text-right">
              <v-chip small :class="`${project.status} white--text my-2 caption`">{{ project.status }}</v-chip>
            </div>
          </v-flex>

        </v-layout>
        <v-divider></v-divider>
      </v-card>
    </v-container>
  </div>
</template>

<script>


export default {
  data(){
    return{
      projects: [
        { title: 'Design a new website', person: 'Chiz', due: '1st Jan 2019', status: 'ongoing', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Code up the homepage', person: 'Chun Li', due: '10th Jan 2019', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Design video thumbnails', person: 'Ryu', due: '20th Dec 2018', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Create a community forum', person: 'Gouken', due: '20th Oct 2018', status: 'overdue', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
      ]
    }
  },
  methods:{
    sortBy(whichtype){
      this.projects.sort((a,b) => a[whichtype]<b[whichtype] ? -1 : 1)
    }
  }

}
</script>

<style>

.project.ongoing {
   border-left: 4px solid orange;
}

.project.overdue{
   border-left: 4px solid tomato;
}

.project.complete{
   border-left: 4px solid #3cd1c2;
}

.v-chip.v-chip--no-color.theme--light.complete{
  background: #3cd1c2;
}
.v-chip.v-chip--no-color.theme--light.ongoing{
  background: #ffaa2c;
}
.v-chip.v-chip--no-color.theme--light.overdue{
  background: #f83e70;
}

</style>
