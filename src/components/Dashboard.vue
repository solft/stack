<template>
  <div>

    <v-navigation-drawer app permanent :mini-variant="drawer.mini">
      <v-toolbar flat>
        <template v-if="drawer.mini">
          <v-btn @click="drawer.mini = !drawer.mini" icon>
            <v-icon>arrow_forward</v-icon>
          </v-btn>
        </template>
        
        
        <template v-if="!drawer.mini">
          <router-link to="/">
            <v-toolbar-title>MY Stack</v-toolbar-title>
          </router-link>
          <v-spacer></v-spacer>
          <v-btn @click="drawer.mini = !drawer.mini" icon>
            <v-icon>arrow_back</v-icon>
          </v-btn>
        </template>
        
      </v-toolbar>

      <v-list>
        <template v-for="(stack, index) in stacks">
          <router-link :to="stack.name" :key="index">
            <v-list-tile class="my-2">
              <v-list-tile-avatar tile>
                <img :src="stack.logo" alt="">
              </v-list-tile-avatar>

              <v-list-tile-content>
                <v-list-tile-title>{{ stack.name }}</v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
          </router-link>
        </template>
      </v-list>
    </v-navigation-drawer>

    <v-toolbar app flat>
      <v-toolbar-title>Test</v-toolbar-title>
    </v-toolbar>

  </div>
</template>

<script>
export default {
  data() {
    return {
      drawer: {
        mini: true
      },
      stacks: [
        { name: 'vue', logo: require('@/assets/logo/vue.png') },
        { name: 'vuetify', logo: require('@/assets/logo/vuetify.svg') },
        { name: 'react', logo: require('@/assets/logo/react.svg') },
        { name: 'kotlin', logo: require('@/assets/logo/kotlin.png') },
        { name: 'android', logo: require('@/assets/logo/android.png') },
        { name: 'dart', logo: require('@/assets/logo/dart.png') },
        { name: 'flutter', logo: require('@/assets/logo/flutter.png') },
        { name: 'graphql', logo: require('@/assets/logo/GraphQL.svg') },
        { name: 'git', logo: require('@/assets/logo/git.png') },
      ]
    }
  }
}
</script>

<style>
a:link {
  color: black;
  text-decoration: none;
}
a:visited {
  color: black;
  text-decoration: none;
}
a:hover {
  color: black;
  text-decoration: underline;
}
</style>
