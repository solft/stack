<template>
  <v-app>
    <Dashboard/>

    <v-content>
      <router-view></router-view>
    </v-content>
  
  </v-app>
</template>

<script>
import Dashboard from './components/Dashboard.vue'

export default {
  name: 'App',
  components: {
    Dashboard    
  }  
}
</script>
