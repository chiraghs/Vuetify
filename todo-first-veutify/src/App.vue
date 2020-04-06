<template>
  <v-app>
   
    <Navbar  class="grey"></Navbar>
     <v-container >
      <router-view class="grey lighten-4"></router-view>
     </v-container>
  </v-app>
</template>

<script>

import Navbar from '@/components/Navbar'

export default {
  name: 'App',

  components: {Navbar},

  data: () => ({
    //
  }),
};
</script>
