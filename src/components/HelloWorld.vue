<template>
  <v-container class="fill-height">
    <v-responsive class="d-flex text-center fill-height">
      <v-item-group multiple>
        <v-container>
          <v-row>
            <v-col v-for="pokemon in pokemons" :key="pokemon.nome" cols="12" md="4">
              <v-item v-slot="{ isSelected, toggle }">
                <v-card :color="isSelected ? 'purple' : ''" class="d-flex align-center" dark height="200"
                  @click="toggle">
                  <v-scroll-y-transition>
                    <div class="text-h3 flex-grow-1 text-center">
                      {{ isSelected? pokemon.numeroPokedex : pokemon.nome }}
                    </div>
                  </v-scroll-y-transition>
                </v-card>
              </v-item>
            </v-col>
          </v-row>
        </v-container>
      </v-item-group>
    </v-responsive>
  </v-container>
</template>

<script >
export default {
  data() {
    return {
      pokemons: [
        {
          nome: "Pikachu",
          nivel: "25",
          numeroPokedex: "26"
        },
        {
          nome: "Charmander",
          nivel: "25",
          numeroPokedex: "4"
        },
        {
          nome: "Squirte",
          nivel: "25",
          numeroPokedex: "7"
        },
        {
          nome: "Bulbassauro",
          nivel: "25",
          numeroPokedex: "1"
        },
      ]
    }
  }
}
</script>
