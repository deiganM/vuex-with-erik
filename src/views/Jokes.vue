<template>
  <div class="about">
    <h1>This is all the jokes you've retrieved</h1>
    <!-- displays a list of all the jokes you've seen -->
    <h4 v-for="(joke, index) in jokes" :key="index">
      <span>{{ index + 1 }}</span>
      {{ joke }}
    </h4>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
export default {
  computed: {
    ...mapGetters({ jokes: 'getAllJokes' }),
    // jokes() {
    //   return this.$store.getters.getAllJokes
    // },
  },
}
</script>
