<template>
  <div id="app row container-fluid px-0">
    <div class="col-12 px-0 d-flex flex-row overflow">
      <img id="scroll" src="./assets/picture.jpg" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
};
</script>

<style lang="scss">
img {
  height: 45rem;
  animation-direction: normal;
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
