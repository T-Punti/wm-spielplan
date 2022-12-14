<template>
  <Suspense>
    <template #default>
      <Body />
    </template>
    <template #fallback>
      <span>Loading ...</span>
    </template>
  </Suspense>
</template>

<script>
import Body from './components/Body.vue';

export default {
  name: 'App',
  components: {
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
  color: black;
  margin-top: 20px;
}
body {
  background: url('https://img.freepik.com/premium-vector/qatar-2022-fifa-world-cup-background-image-maroon-color-background_741253-3.jpg?w=2000')
    fixed;
}
</style>
