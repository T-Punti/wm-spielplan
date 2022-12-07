<template>
  <div class="gruppe">
    <h2>{{ gruppe.group }}</h2>
    <div v-for="members in gruppe.members">
      <span class="head">
       {{ members.date }}
      {{ members.time }}
      <br>
      </span>
        {{ members.teams[0].team1 }} : {{ members.teams[1].team2 }}
        ({{ members.teams[2].goals_team1 }} : {{ members.teams[3].goals_team2 }})
      </div>
    </div>
    <div v-for="country in flags">
      <img :src="country.link" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Gruppe',
  props: {
    gruppe: Object,
    flags: Array,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .head {
  font-weight: bold;

  }
</style>
