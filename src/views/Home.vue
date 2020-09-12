<template>
  <div id="fullscreen">
    <div id="orientationPortrait">
      <v-img class="titleLogoImgPortrait" src="@/assets/img/titleLogo.png" aspect-ratio="1.4"></v-img>
      <div class="cautionText">
        <h2>画面を横にしてください！</h2>
      </div>
    </div>
    <div id="orientationLandscape">
      <v-img class="ebiImg" src="@/assets/img/LunaEbi.jpg" aspect-ratio="1.4"></v-img>
      <v-img class="titleLogoImg" src="@/assets/img/titleLogo.png" aspect-ratio="1.4"></v-img>
      <div class="toHomeButton">
        <router-link to="/Drum">
          <v-btn color="#FFFFFF" outlined dark large
            width="40vw"
            height="50px"
          >
            ENTER
          </v-btn>
        </router-link>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Home',
  components: {
  }
}
</script>
<style lang="scss" scoped>
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
      animation: Flash1 0.9s linear 0s 1;
    }
    .cautionText {
      position: absolute;
      top: calc(50% - 25px);
      right: 0;
      left: 0;
      animation: Flash1 0.9s linear 0s 1;
      text-align: center;
      font-weight: bold;
      font-size: 15px;
    }
    h2 {
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
    .ebiImg {
      position: absolute;
      width: 40vw;
      top: calc(50% - 30vw/2);
      left: calc(25% - 40vw/2);
      animation: poyooon 0.9s linear 0s 1;
    }
    .titleLogoImg {
      position: absolute;
      width: 40vw;
      top: 12%;
      right: calc(25% - 40vw/2);
      animation: poyooon 0.9s linear 0s 1;
    }
    .toHomeButton {
      position: absolute;
      background: red;
      top: calc(85% - 50px/2);
      right: 5vw;
    }
    a {
      // color: white;
      text-decoration: none;
    }
  }
@keyframes Flash1{
  50%{
    opacity: 0;
  }
}
@keyframes poyooon {
  0%   { transform: scale(1.0, 1.0) translate(0%, 0%); }
  10%  { transform: scale(1.1, 0.9) translate(0%, 5%); }
  40%  { transform: scale(1.2, 0.8) translate(0%, 15%); }
  50%  { transform: scale(1.0, 1.0) translate(0%, 0%); }
  60%  { transform: scale(0.9, 1.2) translate(0%, -100%); }
  75%  { transform: scale(0.9, 1.2) translate(0%, -20%); }
  85%  { transform: scale(1.2, 0.8) translate(0%, 15%); }
  100% { transform: scale(1.0, 1.0) translate(0%, 0%); }
}
</style>
