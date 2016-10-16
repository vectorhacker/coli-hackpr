<template>
<div class="slide-selector">
  <a href="#" @click="back" v-show="notBegining">
    <arrow type="back" class="center-down left"></arrow>
  </a>
  <div class="section-slider" v-bind:is="currentView" :categories="categories">
  </div>
  <a href="#" @click="next" v-show="notEnd">
    <arrow type="forward" class="center-down right"></arrow>
  </a>
</div>
</template>

<script>
import Arrow from "./Arrow"
import Age from "./Age"
import Diet from "./Diet"
import Housing from "./Housing"
import Transportation from "./Transportation"
import Results from "./Results"

export default {
  data() {
    return {
      index: 0,
      views: ["age", "diet", "housing", "transportation", "results"],
      categories: {
        "grocery": [
          "22",
          "21",
          "20",
          "10",
          "11",
          "12",
          "13",
          "14",
          "15",
          "16",
          "17",
          "18",
          "19",
          "24",
          "25",
          "26"
        ],
        "housing": [
          "29",
          "30",
          "29+30"
        ],
        "transportation": [
        ],
        "health care": [
          "34",
          "35",
          "36"
        ],
        "miscellaneous": [
          "39",
          "40",
          "41",
          "42",
          "43",
          "44",
          "45",
          "46",
          "47",
          "48",
          "49",
          "50",
          "51",
          "52",
          "53",
          "54",
          "55",
          "56",
          "57"
        ]
      }
    }
  },
  components: {
    Arrow,
    Age,
    Diet,
    Housing,
    Transportation,
    Results
  },
  methods: {
    next() {
      this.index += 1;
    },
    back() {
      this.index -= 1;
    }
  },
  computed: {
    currentView() {
      return this.views[this.index];
    },
    notBegining() {
      console.log(this.views.length)
      return this.index !== 0
    },
    notEnd() {
      return this.index !== this.views.length - 1
    }
  }
}
</script>

<style>
.section-slider {
  width: auto;
  height: 300px;
  float: left;
  padding-left: 128px;
  padding-right: 128px;
}
</style>
