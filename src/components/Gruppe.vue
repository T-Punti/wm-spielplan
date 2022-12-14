<template>
  <div class="gruppe">
    <h2>{{ gruppe.group }}</h2>

    <div v-for="members in gruppe.members">
      <table>
        <thead>
          <tr>
            <th>{{ members.date }}</th>
            <th>{{ members.time }}</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td class="flag">
              <div v-for="flag in flags">
                <div
                  v-if="flag.country == members.teams[0].team1.toLowerCase()"
                >
                  <img :src="flag.link" :alt="" heigth="5" />
                </div>
              </div>
            </td>

            <td>{{ members.teams[0].team1 }}</td>
            <td>{{ members.teams[2].goals_team1 }}</td>
          </tr>
          <tr>
            <td class="flag">
              <div v-for="flag in flags">
                <div
                  v-if="flag.country == members.teams[1].team2.toLowerCase()"
                >
                  <img :src="flag.link" :alt="" heigth="5" />
                </div>
              </div>
            </td>
            <td>{{ members.teams[1].team2 }}</td>
            <td>{{ members.teams[3].goals_team2 }}</td>
          </tr>
        </tbody>
      </table>
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
table {
  text-align: left;
  margin: auto;
}
.gruppe {
  border: 1px solid black;
  margin: auto;
  margin-bottom: 10px;
  width: 75%;
  background: rgba(184, 184, 184, 0.5);
}
.flag {
  text-align: center;
}
</style>
