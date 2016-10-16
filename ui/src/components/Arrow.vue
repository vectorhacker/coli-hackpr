<template>
  <div v-bind:class="arrow"></div>
</template>

<script>
export default {
  props: [
    'type'
  ],
  computed: {
    arrow() {
      return {
        "arrow arrow_back": this.type === "back",
        "arrow arrow_forward": this.type === "forward"
      }
    }
  }
}
</script>

<style>
.arrow {
  background-size: contain;
  width: 64px;
  height: 64px;
}

.arrow:hover {
  cursor: pointer;
}

.arrow_back {
  background-image: url("../assets/icons/png/back.png");
  background-size: contain;
}

.arrow_forward {
  background-image: url("../assets/icons/png/next.png");
}
</style>
