<template>
  <div class="home d-flex justify-center pa-5"
       style="height: calc(100vh - 56px)">
        <v-btn @click="createCharacter">Create a character</v-btn>
  </div>
</template>

<script>
export default {
  name: 'Home',
  methods: {
    createCharacter () {
      console.log('create')
    }
  }
}
</script>
