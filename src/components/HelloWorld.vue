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
                      {{ isSelected? "Nível: "+ pokemon.nivel : pokemon.nome }}
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

<script>
import axios from 'axios';

export default {
  data() {
    return {
      pokemons: [
      ]
    }
  },
  mounted() {
    axios.get("http://localhost:8080/pokemons/").then((resposta) => {
      this.pokemons = resposta.data;
    }).catch((erro) => {
      console.log(erro);
    });
  }
}
</script>
