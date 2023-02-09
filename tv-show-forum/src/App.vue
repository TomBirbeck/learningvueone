<script>
import AverageAge from './components/AverageAge.vue'
import CharacterCard from './components/CharacterCard.vue';
export default {
    data() {
        return {
            listOfChars: [
                { name: "Steve", age: 40 },
                { name: "John", age: 30 },
                { name: "Dave", age: 23 },
            ],
            noCharsMessage: "No characters found",
            favouriteList: [],
            newCharacter: {
                name: "",
                age: 0
            },
        };
    },
    methods: {
        addFavouriteCharacter(payload) {
            this.favouriteList.push(payload);
        },
        addNewCharacter() {
            this.listOfChars.push(this.newCharacter);
            this.newCharacter = { name: "" };
        }
    },
    components:  {AverageAge, CharacterCard} 
}
</script>

<template>
    <ul v-if="listOfChars.length > 0">
      <li v-for="(character, index) in listOfChars"
      :key="`character-${index}`">
        <CharacterCard v-bind:character="character"
        @favourite="addFavouriteCharacter"/>
      </li>
        </ul>
        <p v-else>{{noCharsMessage}}</p>
        <h2>Favourite Characters</h2>
        <ul v-if="favouriteList.length > 0">
            <li v-for="(character, index) in favouriteList" v-bind:key="`character-${i}`">{{character.name}}</li>
        </ul>
        <p v-else>Please select a favourite</p>
        <h2>New Character</h2>
        <lable for="character-name">Name</lable>
        <input type="text" v-model="newCharacter.name" @keyUp.enter="addNewCharacter"/>
        <pre>
            {{newCharacter}}
        </pre>
        <AverageAge v-bind:characters="listOfChars"/>
    <!-- <h2>Average Age</h2> -->
    <!-- <p>{{averageAgeCalculation}}</p> -->
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
