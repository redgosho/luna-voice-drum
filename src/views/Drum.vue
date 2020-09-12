<template>
  <v-container class="text-center drum">
    <div class="my-2">
      <v-btn color="error" dark large>
        <v-icon>mdi-arrowLeft-bold</v-icon>
      </v-btn>
    </div>
    <v-responsive
      class="text-center grey lighten-2 rounded-pill d-inline-flex align-center justify-center ma-3"
      height="200"
      width="200"
      @click="playSound(decision3)"
    >
      Pill
    </v-responsive>

    <v-responsive
      class="text-center grey lighten-2 rounded-circle d-inline-flex align-center justify-center ma-3"
      height="64"
      width="64"
    >
      Circle
    </v-responsive>
  </v-container>
</template>
<script>
import decision3 from '@/assets/sounds/decision3.mp3'
import decision18 from '@/assets/sounds/decision18.mp3'
export default {
  data () {
    return {
      decision3: decision3,
      decision18: decision18
    }
  },
  methods: {
    playSound (soundName) {
      const audio = new Audio(soundName)
      audio.volume = 1
      audio.play()
    }
  }
}
</script>
