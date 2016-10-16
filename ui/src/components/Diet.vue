<template>
  <div id="diet">
    <h3 class="title">What's your diet?</h3>

    <div @click="select('omnivore')" v-bind:class="['diet', 'diet--omnivore', {diet__selected: selected === 'omnivore'}]">
      <h4 class="age_title">Omnivore</h4>
    </div>
    <div @click="select('vegan')" v-bind:class="['diet', 'diet--vegan', {diet__selected: selected === 'vegan'}]">
      <h4 class="age_title">Vegan</h4>
    </div>
    <div @click="select('vegetarian')" v-bind:class="['diet', 'diet--vegetarian', {diet__selected: selected === 'vegetarian'}]">
      <h4 class="age_title">Vegitarian</h4>
    </div>
  </div>
</template>

<script>
let diets = {
  "vegetarian": [
    "6",
    "7"
  ],
  "omnivore": [
    "1",
    "2",
    "3",
    "4",
    "5",
    "23"
  ]
}

export default {
  data() {
    return {
      "selected": "none"
    }
  },
  props: [
    "categories"
  ],
  components: {
  },
  methods: {
    select(selection) {
      this.selected = selection
      switch (selection) {
      case "omnivore":
        this.categories["grocery"] = this.categories["grocery"].concat(diets["omnivore"])
      case "vegan":
        this.categories["grocery"] = this.categories["grocery"].concat(diets["vegan"])
        break;
      default:

      }
    }
  }
}
</script>

<style>
.diet {
  margin: 0 25px;
  border-radius: 50%;
  border-color: #FEC606;
  border-width: 1px;
  float: left;
  width: 128px;
  height: 128px;
  background-size: 100px 100px;
  background-repeat: no-repeat;
  background-position: center;
}

.diet:hover {
  cursor: pointer;
}

.diet__selected {
  background-color: #7574A7;
}

.diet--omnivore {
  background-image: url('../assets/icons/png/turkey.png');
}

.diet--vegan {
  background-image: url('../assets/icons/png/bananas.png');
}

.diet--vegetarian {
  background-image: url('../assets/icons/png/potatoes.png');
}
</style>
