<template>
  <div id="fullscreen">
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
