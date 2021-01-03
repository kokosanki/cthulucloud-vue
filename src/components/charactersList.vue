<template>
  <div>
    <h2 class="my-5">Your characters:</h2>
    <ol>
      <li v-for="(character, index) in characters" :key="index">
       {{ character.name }}
      </li>
    </ol>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  computed: {
    ...mapGetters(['characters'])
  }
}
</script>

<style></style>
