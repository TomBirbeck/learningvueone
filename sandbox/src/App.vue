<script>
import BaseCounter from './components/BaseCounter.vue'
import BaseButton from './components/BaseButton.vue'
import BaseLayout from './components/BaseLayout.vue'

export default {
  components: {
    BaseCounter,
    BaseButton,
    BaseLayout
  },
  data() {
                return {
                    message: 'Hello it works',
                    listOfNumbers: [1,2,3,4,5],
                    listOfWords: ['One', 'Two', 'Three', 'Four'],
                                    }
            },
          
            }
</script>

<template>
  <BaseLayout>
    <template v-slot:sidebar>
      <BaseButton :left="true">
      </BaseButton>
    </template>
    <template v-slot:main>
      <hr/>
          <p v-if="message.length % 2 === 0">Even: {{message.toUpperCase()}}</p>
            <p v-else>Odd: {{message}}</p>
            <ul>
                <li v-for="(number, index) in listOfNumbers" v-bind:key="`number-${index}`">{{number}}</li>
            </ul>
    </template>
    <template #footer>
      <BaseCounter/>
    </template>
  </BaseLayout>
        <ul>
            <li v-for="(word, index) in listOfWords" v-bind:key="`word-${index}`">{{word}}</li>
        </ul>
        <hr/>
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
