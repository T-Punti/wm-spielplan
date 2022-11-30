<template>
  <div>
    <div v-if="error">
      <h2>{{ error }}</h2>
    </div>
    <div v-else>
      <div v-if="loading">
        <h2>Loading DATA ...</h2>
      </div>
    </div>
    <div class="Gruppe">
      <div v-for="items in data">
        <div v-for="country in items">
          <img :src="country.link" alt="flag" />
          {{ country.country }}
        </div>
        <div v-for="group in items">
          <Gruppe :gruppe="group" />
        </div>
      </div>
      <div v-for="(item, index) in data.flags" :key="index">
        {{ item.country }}
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
    const { data, error, loading } = useFetch(
      'https://raw.githubusercontent.com/htlWels/WM/main/spielplan.json',
      {}
    );
    return {
      data,
      error,
      loading,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
