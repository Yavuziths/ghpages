<script setup>
import LeagueCard from "../components/LeagueCard.vue";
import Footerbar from "../components/FooterBar.vue";
</script>
<template>
  <div class="spacer">&nbsp;</div>
  <div class="container-fluid">
    <h1 class="fix">
      Här kan du kolla in lag från det fyra största ligorna och lite information
      om dem
    </h1>
    <p class="fix">
      kolla närmare på ditt lag vart det befinnersig och vilken som e just ditt
      lags hemma arena
    </p>
    <div class="row">
      <leagues
        v-for="(league, id) in leagues"
        :key="id"
        :league="league"
        :offer="league"
      />
    </div>
  </div>
  <Footerbar />
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      leagues: [],
    };
  },
  name: "TeamView",
  components: { leagues: LeagueCard },

  mounted() {
    this.fetchData();
  },
  //   axios to fetch data from json
  methods: {
    fetchData() {
      const t = this;
      axios.get("League1.json").then((response) => {
        t.leagues.push({
          img: "https://media.api-sports.io/football/leagues/61.png",
          league: response.data,
        });
      });
      axios.get("PremierLeague.json").then((response) => {
        t.leagues.push({
          img: "https://media.api-sports.io/football/leagues/39.png",
          league: response.data,
        });
      });
      axios.get("Laliga.json").then((response) => {
        t.leagues.push({
          img: "https://media.api-sports.io/football/leagues/140.png",
          league: response.data,
        });
      });
      axios.get("SerieA.json").then((response) => {
        t.leagues.push({
          img: "https://media.api-sports.io/football/leagues/135.png",
          league: response.data,
        });
      });
      //   axios.get("SerieA.json").then((response) => {
      //     t.leagues.push({
      //       img: "https://media.api-sports.io/football/leagues/135.png",
      //       league: response.data,
      //     });
      //   });
    },
  },
};
</script>
<!--här är lite positionerings -->
<style scoped>
.team-view {
  position: absolute;
  top: 5%;
  transform: translate();
}
.spacer {
  width: 100%;
  height: 50px;
}
.row {
  color: rgb(110, 110, 110);
  font-size: larger;
  font-family: sans-serif;
  margin-top: 100px;
}
.fix {
  margin-top: 50px;
  color: rgb(110, 110, 110);
  font-size: larger;
  font-family: sans-serif;
  text-align: center;
}
</style>
