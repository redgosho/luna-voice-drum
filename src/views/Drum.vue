<template>
  <v-container
    id="fullscreen"
    class="text-center drum-area"
  >
    <div id="orientationPortrait">
      <v-img class="titleLogoImgPortrait" src="@/assets/img/titleLogo.png" aspect-ratio="1.4"></v-img>
      <div class="cautionText">
        <h2 class="cautionTextH2">画面を横にしてください！</h2>
      </div>
    </div>
    <div id="orientationLandscape">
      <v-img class="ebiImg" src="@/assets/img/LunaEbi.jpg" aspect-ratio="1.4"></v-img>
      <div class="toHomeButton">
        <router-link to="/">
          <v-btn color="#FFFFFF" outlined dark large>
            <v-icon>mdi-arrow-left-bold</v-icon>
          </v-btn>
        </router-link>
      </div>
      <div class="drum bass">
        <v-btn color="#333631"
          fab x-large dark
          :height="drumSize.bass"
          :width="drumSize.bass"
          @click="playSound(lunaDoon)"
        >
          <v-icon>mdi-surround-sound</v-icon>
        </v-btn>
      </div>
      <div class="drum snare1">
        <v-btn color="#95949a"
          fab x-large dark
          :height="drumSize.snare"
          :width="drumSize.snare"
          @click="playSound(lunaDon)"
        >
          <v-icon>mdi-blur-radial</v-icon>
        </v-btn>
      </div>
      <div class="drum snare2">
        <v-btn color="#95949a"
          fab x-large dark
          :height="drumSize.snare"
          :width="drumSize.snare"
          @click="playSound(lunaTa)"
        >
          <v-icon>mdi-blur-radial</v-icon>
        </v-btn>
      </div>
      <div class="drum snare3">
        <v-btn color="#95949a"
          fab x-large dark
          :height="drumSize.snare"
          :width="drumSize.snare"
          @click="playSound(lunaPun)"
        >
          <v-icon>mdi-blur-radial</v-icon>
        </v-btn>
      </div>
      <div class="drum snare4">
        <v-btn color="#95949a"
          fab x-large dark
          :height="drumSize.snare"
          :width="drumSize.snare"
          @click="playSound(lunaDokan)"
        >
          <v-icon>mdi-blur-radial</v-icon>
        </v-btn>
      </div>
      <div class="drum cymbal1">
        <v-btn color="#fef263"
          fab x-large dark
          :height="drumSize.cymbal"
          :width="drumSize.cymbal"
          @click="playSound(lunaShaaa)"
        >
          <v-icon>mdi-album</v-icon>
        </v-btn>
      </div>
      <div class="drum cymbal2">
        <v-btn color="#fef263"
          fab x-large dark
          :height="drumSize.cymbal"
          :width="drumSize.cymbal"
          @click="playSound(lunaShuuu)"
        >
          <v-icon>mdi-album</v-icon>
        </v-btn>
      </div>
      <div class="drum cymbal3">
        <v-btn color="#fef263"
          fab x-large dark
          :height="drumSize.cymbal"
          :width="drumSize.cymbal"
          @click="playSound(lunaKan)"
        >
          <v-icon>mdi-album</v-icon>
        </v-btn>
      </div>
      <div class="drum cymbal4">
        <v-btn color="#fef263"
          fab x-large dark
          :height="drumSize.cymbal"
          :width="drumSize.cymbal"
          @click="playSound(lunaKatan)"
        >
          <v-icon>mdi-album</v-icon>
        </v-btn>
      </div>
    </div>
  </v-container>
</template>
<script>
import lunaAaa from '@/assets/sounds/lunaAaa.wav'
import lunaAxtsu from '@/assets/sounds/lunaAxtsu.wav'
import lunaDokan from '@/assets/sounds/lunaDokan.wav'
import lunaDon from '@/assets/sounds/lunaDon.wav'
import lunaDoon from '@/assets/sounds/lunaDoon.wav'
import lunaExtsu from '@/assets/sounds/lunaExtsu.wav'
import lunaHai from '@/assets/sounds/lunaHai.wav'
import lunaKan from '@/assets/sounds/lunaKan.wav'
import lunaKatan from '@/assets/sounds/lunaKatan.wav'
import lunaNaaa from '@/assets/sounds/lunaNaaa.wav'
import lunaNn from '@/assets/sounds/lunaNn.wav'
import lunaPun from '@/assets/sounds/lunaPun.wav'
import lunaShaaa from '@/assets/sounds/lunaShaaa.wav'
import lunaShuuu from '@/assets/sounds/lunaShuuu.wav'
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
      lunaAaa: lunaAaa,
      lunaAxtsu: lunaAxtsu,
      lunaDokan: lunaDokan,
      lunaDon: lunaDon,
      lunaDoon: lunaDoon,
      lunaExtsu: lunaExtsu,
      lunaHai: lunaHai,
      lunaKan: lunaKan,
      lunaKatan: lunaKatan,
      lunaNaaa: lunaNaaa,
      lunaNn: lunaNn,
      lunaPun: lunaPun,
      lunaShaaa: lunaShaaa,
      lunaShuuu: lunaShuuu,
      lunaTa: lunaTa,
      lunaYo: lunaYo
    }
  },
  mounted () {
    this.sizeInit()
    // console.log('this.drumSize:', this.drumSize)
  },
  methods: {
    sizeInit () {
      const width = window.innerWidth
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
  @media screen and (orientation: portrait) {
    /* 縦向きの場合のスタイル */
    #orientationPortrait {
      opacity: 1;
    }
    #orientationLandscape {
      opacity: 0;
    }
    .titleLogoImgPortrait {
      position: absolute;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
      margin: auto;
      height: 40vh;
      animation: Flash1 0.9s linear 0s infinite;
    }
    .cautionText {
      position: absolute;
      top: calc(50% - 25px);
      right: 0;
      left: 0;
      animation: Flash1 0.9s linear 0s infinite;
      text-align: center;
      font-weight: bold;
      font-size: 15px;
    }
    .cautionTextH2 {
      padding: 1rem 2rem;
      position: relative;
      color: #ffffff;
      font-size: 25px;
      text-shadow:
       3px  3px 1px #003366,
      -3px  3px 1px #003366,
       3px -3px 1px #003366,
      -3px -3px 1px #003366,
       3px  0px 1px #003366,
       0px  3px 1px #003366,
      -3px  0px 1px #003366,
       0px -3px 1px #003366;
      background: linear-gradient(-45deg, darken(#000000, 3%) 25%, #ffff00 0, #ffff00 50%, darken(#000000, 3%) 0, darken(#000000, 3%) 75%, #ffff00 0);
      background-size: 20px 20px;
    }
  }
  @media screen and (orientation: landscape) {
    /* 横向きの場合のスタイル */
    #orientationPortrait {
      opacity: 0;
    }
    #orientationLandscape {
      opacity: 1;
    }
    .drum-area {
      // position: relative;
      // background: red;
    }
    .ebiImg {
      position: absolute;
      width: 30vw;
      top: calc(0% - 30vw/6);
      left: calc(50% - 30vw/2);
      animation: swing 1s ease-in-out infinite;
    }
    .toHomeButton {
      position: absolute;
      // background: red;
      left: 5px;
      top: 5px;
    }
    a {
      // color: white;
      text-decoration: none;
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
  }
  @keyframes Flash1{
    50%{
      opacity: 0;
    }
  }
  @keyframes swing {
      0% { transform: rotate(0deg); }
      25% { transform: rotate(10deg); }
      50% { transform: rotate(0deg); }
      75% { transform: rotate(-10deg); }
      100% { transform: rotate(0deg); }
  }
</style>
