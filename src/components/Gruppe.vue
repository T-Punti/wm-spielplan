<template>
  <div class="gruppe">
    <h2>{{ gruppe.group }}</h2>
    
  </div>
</template>

<script>
export default {
  name: 'Gruppe',
  props: {
    gruppe: Object,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
