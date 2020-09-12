<template>
  <v-container
    id="fullscreen"
    class="text-center drum-area"
  >
    <div class="my-2">
      <v-btn color="error" dark large>
        <v-icon>mdi-arrowLeft-bold</v-icon>
      </v-btn>
    </div>
    <div class="drum bass">
      <v-btn color="success"
        fab x-large dark
        height="280"
        width="280"
        @click="playSound(decision3)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum snare1">
      <v-btn color="success"
        fab x-large dark
        height="200"
        width="200"
        @click="playSound(decision3)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum snare2">
      <v-btn color="success"
        fab x-large dark
        height="200"
        width="200"
        @click="playSound(decision3)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum snare3">
      <v-btn color="success"
        fab x-large dark
        height="200"
        width="200"
        @click="playSound(decision3)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum snare4">
      <v-btn color="success"
        fab x-large dark
        height="200"
        width="200"
        @click="playSound(decision3)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum cymbal1">
      <v-btn color="success"
        fab x-large dark
        height="150"
        width="150"
        @click="playSound(decision3)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum cymbal2">
      <v-btn color="success"
        fab x-large dark
        height="150"
        width="150"
        @click="playSound(decision3)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum cymbal3">
      <v-btn color="success"
        fab x-large dark
        height="150"
        width="150"
        @click="playSound(decision3)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum cymbal4">
      <v-btn color="success"
        fab x-large dark
        height="150"
        width="150"
        @click="playSound(decision3)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
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
<style lang="scss" scoped>
  $bass: "280px";
  $snare1: "200px";
  $snare2: "200px";
  $cymbal1: "150px";

  #fullscreen {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.233);
  }
  .drum-area {
    // position: relative;
    background: red;
  }
  .drum {
    position: absolute;
    // background: blue;
  }
  .bass {
    bottom: calc(0% - #{$bass}/3);
    left: calc(50% - #{$bass}/2);
  }
  .snare1 {
    bottom: calc(0% - #{$snare1}/3);
    left: calc(75% - #{$snare1}/2);
  }
  .snare2 {
    bottom: calc(0% - #{$snare1}/3);
    left: calc(25% - #{$snare1}/2);
  }
  .snare3 {
    bottom: calc(40% - #{$snare1}/3);
    left: calc(38% - #{$snare1}/2);
  }
  .snare4 {
    bottom: calc(40% - #{$snare1}/3);
    left: calc(62% - #{$snare1}/2);
  }
  .cymbal1 {
    bottom: calc(30% - #{$cymbal1}/3);
    left: calc(13% - #{$cymbal1}/2);
  }
  .cymbal2 {
    bottom: calc(60% - #{$cymbal1}/3);
    left: calc(25% - #{$cymbal1}/2);
  }
  .cymbal3 {
    bottom: calc(60% - #{$cymbal1}/3);
    left: calc(75% - #{$cymbal1}/2);
  }
  .cymbal4 {
    bottom: calc(30% - #{$cymbal1}/3);
    left: calc(87% - #{$cymbal1}/2);
  }
</style>
