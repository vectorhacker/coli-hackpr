<template>
  <div id="diet">
    <h3 class="title">Rent or Own?</h3>

    <div @click="select('renter')" v-bind:class="['housing', 'housing--renter', {housing__selected: selected === 'renter'}]">
      <h4 class="age_title">Rent</h4>
    </div>
    <div @click="select('owner')" v-bind:class="['housing', 'housing--owner', {housing__selected: selected === 'owner'}]">
      <h4 class="age_title">Own</h4>
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
  components: {
  },
  methods: {
    select(selection) {
      this.selected = selection
      switch (selection) {
        case "owner":
          this.categories["housing"].concat(["28A", "28B", "28C"])
          break;
        case "renter":
          this.categories["housing"].concat(["27"])
          break;
      }
    }
  }
}
</script>

<style>
.housing {
  margin: 0 25px;
  border-radius: 50%;
  border-color: #FEC606;
  border-width: 1px;
  float: left;
  width: 128px;
  height: 128px;
  background-size: 90px 90px;
  background-repeat: no-repeat;
  background-position: center;
}

.housing:hover {
  cursor: pointer;
}

.housing__selected {
  background-color: #8BCBDE;
}

.housing--renter {
  background-image: url('../assets/icons/png/flats.png');
}

.housing--owner {
  background-image: url('../assets/icons/png/home.png');
}
</style>
