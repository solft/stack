<template>
  <v-app>

    <v-navigation-drawer app permanent :mini-variant="drawer.mini">
      <v-toolbar flat>
        <template v-if="drawer.mini">
          <v-btn @click="drawer.mini = !drawer.mini" icon>
            <v-icon>arrow_forward</v-icon>
          </v-btn>
        </template>
        
        <template v-if="!drawer.mini">
          <v-toolbar-title>MY Stack</v-toolbar-title>
          <v-spacer></v-spacer>
          <v-btn @click="drawer.mini = !drawer.mini" icon>
            <v-icon>arrow_back</v-icon>
          </v-btn>
        </template>
      </v-toolbar>

      <v-list>
        <template v-for="(stack, index) in stacks">
          <v-list-tile :key="index" class="my-2">
            <v-list-tile-avatar tile>
              <img :src="stack.logo" alt="">
            </v-list-tile-avatar>

            <v-list-tile-content>
              <v-list-tile-title>{{ stack.name }}</v-list-tile-title>
            </v-list-tile-content>

          </v-list-tile>
        </template>
      </v-list>
    </v-navigation-drawer>

    <v-toolbar app flat>
      <v-toolbar-title>Test</v-toolbar-title>
    </v-toolbar>

  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: {
        mini: true
      },
      stacks: [
        { name: 'Vue', logo: require('@/assets/logo/vue.png') },
        { name: 'Vuetify', logo: require('@/assets/logo/vuetify.svg') },
        { name: 'React', logo: require('@/assets/logo/react.svg') },
        { name: 'Kotlin', logo: require('@/assets/logo/kotlin.png') },
        { name: 'Android', logo: require('@/assets/logo/android.png') },
        { name: 'Dart', logo: require('@/assets/logo/dart.png') },
        { name: 'Flutter', logo: require('@/assets/logo/flutter.png') },
        { name: 'GraphQL', logo: require('@/assets/logo/GraphQL.svg') },
        { name: 'Git', logo: require('@/assets/logo/git.png') },
      ]
    }
  }
}
</script>

<style>

</style>
