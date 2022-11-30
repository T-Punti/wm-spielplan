<template>
  <Suspense>
    <template #default>
      <Header msg="WM-Spielplan" />
      <Body />
    </template>
    <template #fallback>
      <span>Loading ...</span>
    </template>
  </Suspense>
</template>

<script>
import Header from './components/Header.vue';
import Body from './components/Body.vue';

export default {
  name: 'App',
  components: {
    Header,
    Body,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}
</style>
