<script setup>
import { ref, defineEmits } from "vue";

defineProps({});

const emit = defineEmits(["filter"]);

function filter(event) {
  emit("filter", event.target.value);
}
</script>

<template>
  <nav>
    <form action="">
      <div class="select-container">
        <div class="select-text">
          <select
            name="Génération"
            id="gen-select"
            @change="filter"
            class="form-control"
          >
            <option value="0">National</option>
            <option value="1">Gen 1</option>
            <option value="2">Gen 2</option>
            <option value="3">Gen 3</option>
            <option value="4">Gen 4</option>
            <option value="5">Gen 5</option>
            <option value="6">Gen 6</option>
            <option value="7">Gen 7</option>
            <option value="8">Gen 8</option>
            <option value="9">Gen 9</option>
          </select>
          <span>v</span>
        </div>
        <div class="hover"></div>
      </div>
      <div class="select-container">
        <div class="select-text">
          <select
            name="type"
            id="type-select1"
            @change="filter"
            class="form-control"
          >
            <option value="0">Type 1</option>
            <option value="Acier">Acier</option>
            <option value="Combat">Combat</option>
            <option value="Dragon">Dragon</option>
            <option value="Eau">Eau</option>
            <option value="Electrik">Électrique</option>
            <option value="Fee">Fée</option>
            <option value="Feu">Feu</option>
            <option value="Glace">Glace</option>
            <option value="Insecte">Insecte</option>
            <option value="Normal">Normal</option>
            <option value="Plante">Plante</option>
            <option value="Poison">Poison</option>
            <option value="Psy">Psy</option>
            <option value="Roche">Roche</option>
            <option value="Sol">Sol</option>
            <option value="Spectre">Spectre</option>
            <option value="Tenebres">Ténèbre</option>
            <option value="Vol">Vol</option>
          </select>
          <span>v</span>
        </div>
        <div class="hover"></div>
      </div>
      <div class="select-container">
        <div class="select-text">
          <select
            name="type"
            id="type-select2"
            @change="filter"
            class="form-control"
          >
            <option value="0">Type 2</option>
            <option value="Acier">Acier</option>
            <option value="Combat">Combat</option>
            <option value="Dragon">Dragon</option>
            <option value="Eau">Eau</option>
            <option value="Electrik">Électrique</option>
            <option value="Fee">Fée</option>
            <option value="Feu">Feu</option>
            <option value="Glace">Glace</option>
            <option value="Insecte">Insecte</option>
            <option value="Normal">Normal</option>
            <option value="Plante">Plante</option>
            <option value="Poison">Poison</option>
            <option value="Psy">Psy</option>
            <option value="Roche">Roche</option>
            <option value="Sol">Sol</option>
            <option value="Spectre">Spectre</option>
            <option value="Tenebre">Ténèbre</option>
            <option value="Vol">Vol</option>
          </select>
          <span>v</span>
        </div>
        <div class="hover"></div>
      </div>
    </form>
  </nav>
</template>

<style scoped>
.select-container {
  display: flex;
  flex-direction: column;
  gap: 4px;
  align-items: center;

  &:hover .hover {
    width: 95%;
  }
}
.hover {
  background-color: var(--text-color);
  height: 3px;
  width: 0%;
  transition: all 0.6s cubic-bezier(0.075, 0.82, 0.165, 1);
}
.select-text {
  display: flex;
  flex-direction: row;
  gap: 10px;
  align-items: center;
}
span {
  font-size: 24px;
  font-weight: 700;
}
form {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  height: 100px;
  gap: 48px;
}
select {
  all: unset;
  height: auto;
  font-size: 32px;
}
</style>
