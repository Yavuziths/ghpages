<template>
  <!-- colums for cards -->
  <div class="col">
    <div class="card league-card" style="width: 18rem">
      <img
        v-if="league.img"
        :src="league.img"
        alt="Team logo"
        style="width: 200px; height: 200px"
      />
      <a @click="toggleTeams()" class="btn btn-primary">Show Teams</a>
      <div v-if="toggledTeams">
        <ul>
          <li
            v-for="team in league.league"
            :key="team.id"
            style="color: black"
            @click="selectTeam(team)"
          >
            <img
              :src="team.team.logo"
              alt="Team logo"
              style="width: 50px; height: 50px"
            />
            {{ team.team.name }}
          </li>
        </ul>
        <div v-if="selectedTeam">
          <h2>{{ selectedTeam.team.name }}</h2>
          <img :src="selectedTeam.team.logo" alt="Team logo" />
          <p>Country: {{ selectedTeam.team.country }}</p>
          <p>Venue: {{ selectedTeam.venue.name }}</p>
          <p>Address: {{ selectedTeam.venue.address }}</p>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    league: {
      required: true,
      type: Object,
    },
  },

  data() {
    return {
      selectedTeam: null,
      toggledTeams: false,
    };
  },
  methods: {
    selectTeam(team) {
      this.selectedTeam = team;
    },
    toggleTeams() {
      this.toggledTeams = !this.toggledTeams;
    },
  },
};
</script>
<!--styling for cards-->
<style scoped>
.card {
  display: inline-block;
  align-items: center;
  display: block;
}
.league-card {
  display: flex;
  align-items: center;
  margin: 10% 0;
  padding: 5% 0;
  cursor: pointer;
  margin-left: 50px;
  margin-right: 50px;
}
.btn {
  margin-top: 10px;
}
</style>
