<script>
export default {
  async setup() {
    const regionName = "Europe";
    const pokedex = await fetch(
      "https://pokeapi.co/api/v2/pokemon?limit=151"
    ).then((response) => response.json());

    return {
      pokedex,
      regionName,
    };
  },
  created() {
    console.log(this.regionName);
  },
  // this would run the method after the initial creation of pokedex.
};
</script>

<template>
  <pre>{{ pokedex }}</pre>
</template>
