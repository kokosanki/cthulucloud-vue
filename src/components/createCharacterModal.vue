<template>
  <v-row justify="center">
    <v-dialog v-model="isActive" persistent max-width="600px">
      <v-card>
        <v-card-title>
          <span class="headline">Create Character</span>
        </v-card-title>
        <v-card-text>
          <v-container>
            <v-row>
              <v-form v-model="isFormValid" ref="form">
                <v-col cols="12" sm="6" md="4">
                  <v-text-field
                    label="Name"
                    v-model="name"
                    :rules="rules"
                    required
                  ></v-text-field>
                </v-col>
                <v-col cols="12" sm="6" md="4">
                  <v-text-field
                    label="Gender"
                    :rules="rules"
                    v-model="gender"
                    required
                  ></v-text-field>
                </v-col>
                <v-col cols="12" sm="6" md="4">
                  <v-text-field
                    label="Race"
                    v-model="race"
                    :rules="rules"
                    required
                  ></v-text-field>
                </v-col>
              </v-form>
            </v-row>
          </v-container>
        </v-card-text>
        <v-card-actions class="justify-center">
          <v-btn color="blue darken-1" text @click="closeModal">
            Close
          </v-btn>
          <v-btn :disabled="!isFormValid" color="blue darken-1" text @click="createCharacter">
            Save
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>

<script>
export default {
  props: {
    isModalActive: {
      type: Boolean,
      required: true
    }
  },
  data () {
    return {
      rules: [
        v => !!v || 'Field is required',
        v =>
          (v && v.length <= 100) ||
          'Field must contain less than 100 characters'
      ],
      name: '',
      gender: '',
      race: '',
      isFormValid: false
    }
  },
  computed: {
    isActive () {
      return this.isModalActive
    }
  },
  methods: {
    createCharacter () {
      console.log(this.name, this.gender, this.race)
      this.closeModal()
    },
    closeModal () {
      this.$emit('close')
      this.clearInputData()
    },
    clearInputData () {
      this.name = ''
      this.gender = ''
      this.race = ''
    }
  }
}
</script>

<style></style>
