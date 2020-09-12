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
        :height="drumSize.bass"
        :width="drumSize.bass"
        @click="playSound(decision3)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum snare1">
      <v-btn color="success"
        fab x-large dark
        :height="drumSize.snare"
        :width="drumSize.snare"
        @click="playSound(decision3)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum snare2">
      <v-btn color="success"
        fab x-large dark
        :height="drumSize.snare"
        :width="drumSize.snare"
        @click="playSound(decision3)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum snare3">
      <v-btn color="success"
        fab x-large dark
        :height="drumSize.snare"
        :width="drumSize.snare"
        @click="playSound(decision3)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum snare4">
      <v-btn color="success"
        fab x-large dark
        :height="drumSize.snare"
        :width="drumSize.snare"
        @click="playSound(decision3)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum cymbal1">
      <v-btn color="success"
        fab x-large dark
        :height="drumSize.cymbal"
        :width="drumSize.cymbal"
        @click="playSound(decision3)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum cymbal2">
      <v-btn color="success"
        fab x-large dark
        :height="drumSize.cymbal"
        :width="drumSize.cymbal"
        @click="playSound(decision3)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum cymbal3">
      <v-btn color="success"
        fab x-large dark
        :height="drumSize.cymbal"
        :width="drumSize.cymbal"
        @click="playSound(decision3)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum cymbal4">
      <v-btn color="success"
        fab x-large dark
        :height="drumSize.cymbal"
        :width="drumSize.cymbal"
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
      drumSize: {
        bass: null,
        snare: null,
        cymbal: null
      },
      decision3: decision3,
      decision18: decision18
    }
  },
  mounted () {
    this.sizeInit()
    console.log('this.drumSize:', this.drumSize)
  },
  methods: {
    sizeInit () {
      const width = window.innerWidth
      console.log('width:', width)
      this.drumSize.bass = width / 3
      this.drumSize.snare = width / 4
      this.drumSize.cymbal = width / 5
    },
    playSound (soundName) {
      const audio = new Audio(soundName)
      audio.volume = 1
      audio.play()
    }
  }
}
</script>
<style lang="scss" scoped>
  $bass: "100vw/3";
  $snare1: "100vw/4";
  $snare2: "100vw/4";
  $cymbal1: "100vw/5";

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
