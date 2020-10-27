<template>
  <div id="app row container-fluid px-0">
    <div id="scroll" class="col-12 px-0 d-flex flex-row overflow">
      <div class="col-12 text-center p-2">
        <button class="btn btn-dark rounded px-4" v-on:click="play">
          Play
        </button>
        <audio class="fixed-bottom" ref="audio" @click="animationStart">
          <source src="./assets/sound.mp3" type="audio/mp3" />
        </audio>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  methods: {
    play() {
      let audio = this.$refs.audio;
      if (audio.paused) {
        audio.play();
        document.getElementById("scroll").style.animationPlayState = "running";
      } else {
        audio.pause();
        document.getElementById("scroll").style.animationPlayState = "paused";
      }
    },
  },
};
</script>

<style lang="scss">
@keyframes animatedBackground {
  from {
    background-position: 0px 0;
  }
  to {
    background-position: -1550px 0;
  }
}
#scroll {
  height: 100vh;
  width: 100%;
  background-image: url("./assets/picture.jpg");
  background-size: cover;
  animation: animatedBackground 212s linear infinite;
  animation-play-state: paused;
}
audio {
  height: 20px;
  width: inherit;
}
::-webkit-scrollbar {
  display: none;
}
.overflow {
  overflow: auto;
  flex-wrap: nowrap;
}
body {
  margin: 0;
}
</style>
