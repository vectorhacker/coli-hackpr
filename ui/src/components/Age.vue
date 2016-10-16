<template>
  <div id="age">
    <h3 class="title">How old are you?</h3>
    <div @click="select('young')" v-bind:class="['age', 'young', {age__selected: selected === 'young'}]">
      <h4 class="age_title">18 to 35</h4>
    </div>
      <div @click="select('old')" v-bind:class="['age', 'old', {age__selected: selected === 'old'}]">
        <h4 class="age_title">35 and up</h4>
      </div>
  </div>
</template>

<script>

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

      if (selection === "old") {
        this.categories["health care"].push(["38", "37"])
      }
    }
  }
}
</script>

<style>
.age {
  margin: 0 25px;
  border-radius: 50%;
  width: 128px;
  height: 128px;
  background-repeat: no-repeat;
  background-position: center;
  background-size: 100px 100px;
  float: left;
}

.age:hover {
  cursor: pointer;
}

.age__selected {
  background-color: #3D8EB9;
}

.age_title {
  padding-top: 135px;
  text-align: center;
  font-size: 1.1em;
}

.old {
  background-image: url('../assets/icons/png/manager.png');
}

.young {
  background-image: url('../assets/icons/png/girl.png');
}
</style>
