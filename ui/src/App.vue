<template>
<div class="app">
  <section-slider></section-slider>
</div>
</template>

<script>
import SectionSlider from "./components/SectionSlider"

export default {
  components: {
    SectionSlider
  }
}
</script>

<style>
html {
  height: 100%;
  width: 100%;
}

body {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  width: 100%;
  font-family: "Helvetica", "Arial", sans-serif;
}

.center-down {
  display: block;
  align-items: center;
  justify-content: center;
  margin-top: 10%;
}

.left {
  float: left;
  position: absolute;
  left: 0
}

.right {
  float: left;
  position: absolute;
  left: 95%;
}

.title {
  font-size: 1.5em;
  margin-bottom: 2em;
  text-align: center;
}

.calc-drop {
  padding: 0;
  margin: 0;
  border: 1px solid #ccc;
  width: 120px;
  border-radius: 3px;
  overflow: hidden;
  background-color: #fff;
  text-align: center;
  background: #fff url("http://www.scottgood.com/jsg/blog.nsf/images/arrowdown.gif") no-repeat 90% 50%;
}
</style>
