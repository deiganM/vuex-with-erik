<template>
  <div>
    <h2>I can haz Dad Jokes</h2>
    <h3>{{ joke }}</h3>
    <button @click="addJoke">Add Joke</button>
  </div>
</template>

<script>
// @ is an alias to /src
import { mapActions, mapGetters } from 'vuex'
export default {
  name: 'Home',
  methods: {
    ...mapActions({ addJoke: 'updateCurrentJoke' }),
    // addJoke() {
    // this is replaced by:
    // import { mapActions } from 'vuex' and
    //...mapActions(['updateCurrentJoke']),
    // this.$store.dispatch('updateCurrentJoke')
    //   this.updateCurrentJoke()
    // },
  },
  computed: {
    // I don't understand why this is better as an object
    ...mapGetters({ joke: 'getCurrentJoke' }),
    //   joke() {
    //     return this.$store.getters.getCurrentJoke
    //   },
    // },
    // mounted() {
    //   this.joke = this.$store.getters.getCurrentJoke
  },
}
</script>
