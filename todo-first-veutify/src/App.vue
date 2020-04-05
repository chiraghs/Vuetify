<template>
  <v-app>
   
    <Navbar></Navbar>
     <v-content class="mx-3 mb-5">
      <router-view></router-view>
     </v-content>
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
