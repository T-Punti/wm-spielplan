<template>
  <div v-if="ready">
    <Header msg="WM-Spielplan" />
    <div v-if="error">
      <h2>{{ error }}</h2>
    </div>
    <div v-else>
      <div v-if="loading">
        <h2>Loading DATA ...</h2>
      </div>
    </div>
    <div class="Gruppe">
      <div v-for="group in data.groups">
        <Gruppe :gruppe="group" :flags="flags" />
      </div>
    </div>
  </div>
</template>

<script>
import { useFetch } from '../compose/UseFetch.js';
import Gruppe from './Gruppe.vue';
import Header from './Header.vue';

export default {
  name: 'Body',
  components: {
    Gruppe,
    Header,
  },
  async setup() {
    const { error, loading, ready, data } = useFetch(
      'https://raw.githubusercontent.com/htlWels/WM/main/spielplan.json',
      {}
    );
    const flags = data.flags;
    return {
      data,
      error,
      ready,
      loading,
      flags,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
