<template>
  <div class="header">
    <header>
      <h1>{{ msg }}</h1>
    </header>
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  border-bottom: 1px solid;
  color: rgba(184, 184, 184, 1);
}
</style>
