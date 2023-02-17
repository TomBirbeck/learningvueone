<script>
import { ref, computed, reactive } from "vue";

export default {
  async setup() {
    const regionName = ref("Europe");
    const state = reactive({
      day: "Friday",
    });

    const dayToAllCaps = state.day.toUpperCase();
    const regionAllCaps = computed(() => {
      return regionName.value.toUpperCase();
    });

    const pokedex = await fetch(
      "https://pokeapi.co/api/v2/pokemon?limit=151"
    ).then((response) => response.json());

    return {
      dayToAllCaps,
      pokedex,
      regionName,
      regionAllCaps,
    };
  },
  methods: {
    changeRegionName() {
      this.regionName = "Hoenn";
    },
  },
  created() {
    console.log(this.regionName);
  },
  // this would run the method after the initial creation of pokedex.
};
</script>

<template>
  <h2>{{ regionName }}</h2>
  <h3>{{ regionAllCaps }}</h3>
  <h4>{{ dayToAllCaps }}</h4>
  <button v-on:click="changeRegionName">Change Region Name</button>
  <pre>{{ pokedex }}</pre>
</template>
