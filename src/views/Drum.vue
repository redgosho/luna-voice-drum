<template>
  <v-container
    id="fullscreen"
    class="text-center drum-area"
  >
    <v-img class="ebiImg" src="@/assets/img/LunaEbi.jpg" aspect-ratio="1.4"></v-img>
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
        @click="playSound(lunaNn)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum snare1">
      <v-btn color="success"
        fab x-large dark
        :height="drumSize.snare"
        :width="drumSize.snare"
        @click="playSound(lunaTa)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum snare2">
      <v-btn color="success"
        fab x-large dark
        :height="drumSize.snare"
        :width="drumSize.snare"
        @click="playSound(lunaYo)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum snare3">
      <v-btn color="success"
        fab x-large dark
        :height="drumSize.snare"
        :width="drumSize.snare"
        @click="playSound(lunaHai)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum snare4">
      <v-btn color="success"
        fab x-large dark
        :height="drumSize.snare"
        :width="drumSize.snare"
        @click="playSound(lunaExtsu)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum cymbal1">
      <v-btn color="success"
        fab x-large dark
        :height="drumSize.cymbal"
        :width="drumSize.cymbal"
        @click="playSound(lunaAxtsu)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum cymbal2">
      <v-btn color="success"
        fab x-large dark
        :height="drumSize.cymbal"
        :width="drumSize.cymbal"
        @click="playSound(lunaShaaa)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum cymbal3">
      <v-btn color="success"
        fab x-large dark
        :height="drumSize.cymbal"
        :width="drumSize.cymbal"
        @click="playSound(lunaKatan)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
    <div class="drum cymbal4">
      <v-btn color="success"
        fab x-large dark
        :height="drumSize.cymbal"
        :width="drumSize.cymbal"
        @click="playSound(lunaNaaa)"
      >
        <v-icon>mdi-domain</v-icon>
      </v-btn>
    </div>
  </v-container>
</template>
<script>
import lunaAxtsu from '@/assets/sounds/lunaAxtsu.wav'
import lunaExtsu from '@/assets/sounds/lunaExtsu.wav'
import lunaHai from '@/assets/sounds/lunaHai.wav'
import lunaKatan from '@/assets/sounds/lunaKatan.wav'
import lunaNaaa from '@/assets/sounds/lunaNaaa.wav'
import lunaNn from '@/assets/sounds/lunaNn.wav'
import lunaShaaa from '@/assets/sounds/lunaShaaa.wav'
import lunaTa from '@/assets/sounds/lunaTa.wav'
import lunaYo from '@/assets/sounds/lunaYo.wav'
export default {
  data () {
    return {
      drumSize: {
        bass: null,
        snare: null,
        cymbal: null
      },
      lunaAxtsu: lunaAxtsu,
      lunaExtsu: lunaExtsu,
      lunaHai: lunaHai,
      lunaKatan: lunaKatan,
      lunaNaaa: lunaNaaa,
      lunaNn: lunaNn,
      lunaShaaa: lunaShaaa,
      lunaTa: lunaTa,
      lunaYo: lunaYo
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
    background: #fe91b0;
  }
  .drum-area {
    // position: relative;
    background: red;
  }
  .ebiImg {
    width: 30vw;
    top: calc(0% - 30vw/5);
    left: calc(50% - 30vw/2);
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
    left: calc(25% - #{$snare1}/2);
  }
  .snare2 {
    bottom: calc(40% - #{$snare1}/3);
    left: calc(38% - #{$snare1}/2);
  }
  .snare3 {
    bottom: calc(40% - #{$snare1}/3);
    left: calc(62% - #{$snare1}/2);
  }
  .snare4 {
    bottom: calc(0% - #{$snare1}/3);
    left: calc(75% - #{$snare1}/2);
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
