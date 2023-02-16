<template>
  <div id="wrapper-hero">
    <img
      src="../assets/img/photo-1556056504-5c7696c4c28d.avif"
      class="img-fluid"
      alt="field"
    />
    <div class="centered">
      <h1>Hitta information om ditt lag här</h1>
      <a :href="livescoreUrl"
        >Gå till livescores för att följa ditt lag live genom att klicka på mig
        eller skriva in någon av dessa seriea, premierleague, laliga, league1
        för med enter o ta dig dit direkt
      </a>
      <input type="text" v-model="searchQuery" @keyup.enter="search" />
    </div>
  </div>
</template>
<!--v model search with shortcut to get to seriea laliga ligue1 or premier league instantly
  instead of clicking link to get there you can simply write the league name in search and press enter-->
<script>
export default {
  data() {
    return {
      livescoreUrl: "https://www.livescore.com/en/",
      searchQuery: "",
    };
  },
  methods: {
    search() {
      const query = this.searchQuery.toLowerCase();
      let url = this.livescoreUrl + "football/";

      if (query === "premierleague") {
        url += "england/premier-league/";
      } else if (query === "laliga") {
        url += "spain/laliga-santander/";
      } else if (query === "seriea") {
        url += "italy/serie-a/";
      } else if (query === "league1") {
        url += "france/ligue-1/";
      } else {
        // invalid query
        return;
      }

      window.location.href = url;
    },
  },
};
</script>

<style scoped>
/* hero image styling */
#wrapper-hero {
  position: relative;
}

#wrapper-hero img {
  width: 100%;
}

.centered {
  text-align: center;
  position: absolute;
  top: 30%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: whitesmoke;
}

.centered a {
  color: whitesmoke;
  font-weight: bold;
  margin-top: 20px;
  display: block;
}

.centered input[type="text"] {
  margin-top: 20px;
  padding: 10px;
  width: 50%;
  border-radius: 4px;
  border: none;
  font-size: 16px;
}
</style>
