<template>
  <div v-if="ready">
    <div v-if="error">
      <h2>{{ error }}</h2>
    </div>
    <div v-else>
      <div v-if="loading">
        <h2>Loading DATA ...</h2>
      </div>
    </div>
    <div class="Gruppe">
      <div v-for="country in data.flags">
        <img :src="country.link" alt="flag" /> 
        {{ country.country }}
      </div>
      <div v-for="group in data.groups">
        <Gruppe :gruppe="group" />
      </div>
    </div>
  </div>
</template>

<script>
import { useFetch } from '../compose/UseFetch.js';
import Gruppe from './Gruppe.vue';

export default {
  name: 'Body',
  components: {
    Gruppe,
  },
  async setup() {
    const { error, loading, ready, data } = useFetch(
      'https://raw.githubusercontent.com/htlWels/WM/main/spielplan.json',
      {}
    );
    return {
      data,
      error,
      ready,
      loading,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
