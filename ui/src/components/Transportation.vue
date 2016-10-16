<template>
  <div id="diet">
    <h3 class="title">Drive or Ride?</h3>

    <div @click="select('driver')" v-bind:class="['transportation', 'transportation--driver', {transportation__selected: selected === 'driver'}]">
      <h4 class="age_title">Drive</h4>
    </div>
    <div @click="select('rider')" v-bind:class="['transportation', 'transportation--rider', {transportation__selected: selected === 'rider'}]">
      <h4 class="age_title">Ride</h4>
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
    }
  }
}
</script>

<style>
.transportation {
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

.transportation:hover {
  cursor: pointer;
}

.transportation__selected {
  background-color: #2CC990;
}

.transportation--rider {
  background-image: url('../assets/icons/png/bus.png');
}

.transportation--driver {
  background-image: url('../assets/icons/png/transport.png');
}
</style>
