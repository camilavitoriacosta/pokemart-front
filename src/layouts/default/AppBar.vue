<template>
  <v-app-bar prominent color="purple">
    <template v-slot:prepend>
      <v-app-bar-nav-icon variant="text" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
    </template>
    <v-app-bar-title>
      Pokemart
    </v-app-bar-title>
  </v-app-bar>

  <v-navigation-drawer v-model="drawer" location="top" temporary>
    <v-list density="comfortable" :items="menus">
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      menus:[
        {
          title: "Pokemons",
          value: "/pokemons"
        }
      ]
    }
  }
}
</script>
