<template>
  <div class="home d-flex flex-column justify-center pa-5"
       style="height: calc(100vh - 56px)">
       <div></div>
        <v-btn @click="createCharacter">Create a character</v-btn>
        <characters-list />
        <createCharacterModal @close="closeModal" :isModalActive="isModalActive"/>
  </div>
</template>

<script>
import createCharacterModal from '@/components/createCharacterModal.vue'
import charactersList from '@/components/charactersList.vue'

export default {
  name: 'Home',
  components: {
    createCharacterModal,
    charactersList
  },
  data () {
    return {
      isModalActive: false
    }
  },
  methods: {
    createCharacter () {
      this.isModalActive = true
    },
    closeModal () {
      this.isModalActive = false
    }
  }
}
</script>
