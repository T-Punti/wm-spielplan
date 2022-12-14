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
  background: url('https://img.freepik.com/free-photo/celebrating-football-3d-illustration_1419-2824.jpg?w=1380&t=st=1671005717~exp=1671006317~hmac=898ac4618c678832c0aa06f68b5af37e4daeb62170ffa821a1e20b2331ceaf93')
    fixed;
  background-size: 100% 100%;
}
</style>
