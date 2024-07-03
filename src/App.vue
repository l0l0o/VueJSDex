<script setup>
import { ref, computed, onMounted } from "vue";
import Entete from "./components/Entete.vue";
import Card from "./components/Card.vue";
import CardHover from "./components/CardHover.vue";

// Create ref to store all pkmn
const pkmnList = ref([]);
let pkmnURL = String;

//Fetch all items on mounted app
const fetchAllPkmn = async (filter) => {
  if (filter == null || filter == 0) {
    pkmnURL = "https://tyradex.tech/api/v1/pokemon";
  } else {
    if (!isNaN(filter)) {
      pkmnURL = `https://tyradex.tech/api/v1/gen/${filter}`;
    } else {
      pkmnURL = `https://tyradex.tech/api/v1/types/${filter}`;
    }
  }

  try {
    const response = await fetch(pkmnURL);
    const data = await response.json();
    console.log("Fetched data:", data);

    if (isNaN(filter) && filter != null) {
      pkmnList.value = data.pokemons;
    } else {
      pkmnList.value = data;
    }
  } catch (error) {
    console.error("Error fetching data:", error);
  }
};

onMounted(() => {
  console.log("On mounted app");

  fetchAllPkmn();
  console.log("Initial pkmnList:", pkmnList);
});
</script>

<template>
  <Entete @filter="fetchAllPkmn" />
  <div id="screenSize">
    <div class="corps">
      <div class="wrapper">
        <Card
          v-for="pkmn in pkmnList"
          :key="pkmn.id"
          :pkmnName="pkmn.name.fr"
          :pkmnID="pkmn.pokedex_id"
          :pkmnImage="pkmn.sprites.regular"
        />
        <CardHover id="cardHover" />
      </div>
    </div>
  </div>
</template>

<style scoped>
#screenSize {
  height: 100%;
}
.corps {
  display: flex;
  justify-content: center;
}
.wrapper {
  width: 906px;
  height: 100%;
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
}
#cardHover {
  display: none;
}
</style>
