<template>
  <div>
    <h1>Bandas</h1>
    <FormButton title="Buscar Bandas" :onClick="fetchBands" />
    <ListItems :items="bands" />
    <p v-if="bands.length === 0">Clique no botão para buscar as bandas</p>
  </div>
</template>

<script>
import axios from 'axios';
import FormButton from './components/FormButton.vue';
import ListItems from './components/ListItems.vue';

export default {
  components: {
    FormButton,
    ListItems,
  },
  data() {
    return {
      bands: [],
    };
  },
  methods: {
    fetchBands() {
      axios.get("https://run.mocky.io/v3/b6036826-1ba2-4aed-9143-0c8eb6959eb4", { responseType: 'json' })
        .then((response) => {
          this.bands = response.data;
        })
        .catch((error) => {
          console.error("Erro ao tentar consultar as bandas: ", error);
        });
    },
  },
};
</script>
