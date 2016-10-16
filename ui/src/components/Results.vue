<template>
<div id="results">
  <h3 class="title">Results</h3>
  <div class="result-text">
    If you earn in Puerto Rico $<input class="result-input" v-model="salary"> in <select class="calc-drop" name="state" v-model="selectedState">
        <option v-for="state in states" :value="state">{{ state.name }}</option>
    </select>
    <select class="calc-drop" name="city" v-model="selectedCity" v-if="selectedState.hasOwnProperty('cities')">
      <option v-for="city in selectedState.cities" :value="city ? city : {}">
        {{ city.name }}
      </option>
    </select>you would need ${{ salaryNeeded }} in

  </div>
</div>
</template>

<script>
export default {
  data() {
    return {
      "salary": 40000,
      "selectedState": {},
      "selectedCity": {},
      "states": [{
        "name": "Alabama",
        "cities": [
          {
            "name": "Fake",
            "id": "",
            "index": 10
          }
        ]
      }, {
        "name": "Alaska"
      }, {
        "name": "Arizona"
      }, {
        "name": "Arkansas"
      }, {
        "name": "California",
        "selected": true,
        "cities": [{
          "name": "San Fransisico",
          "id": "288d8ads",
          "index": "40"
        }, {
          "name": "Las Angeles",
          "id": "999sdss",
          "index": "30"
        }]
      }, {
        "name": "Colorado"
      }, {
        "name": "Connecticut"
      }, {
        "name": "Delaware"
      }, {
        "name": "Florida"
      }, {
        "name": "Georgia"
      }, {
        "name": "Hawaii"
      }, {
        "name": "Idaho"
      }, {
        "name": "Illinois"
      }, {
        "name": "Idiana"
      }, {
        "name": "Iowa"
      }, {
        "name": "Kansas"
      }, {
        "name": "Kentucky"
      }, {
        "name": "Lousiana"
      }, {
        "name": "Maine"
      }, {
        "name": "Maryland"
      }, {
        "name": "Massachusetts"
      }, {
        "name": "Michigan"
      }, {
        "name": "Minnesota"
      }, {
        "name": "Mississippi"
      }, {
        "name": "Missouri"
      }, {
        "name": "Montana"
      }, {
        "name": "Nebraska"
      }, {
        "name": "Nevada"
      }, {
        "name": "New Hamshire"
      }, {
        "name": "New Jersey"
      }, {
        "name": "New  Mexico"
      }, {
        "name": "New York"
      }, {
        "name": "North Carolina"
      }, {
        "name": "North Dakota"
      }, {
        "name": "Ohiao"
      }, {
        "name": "Oklahoma"
      }, {
        "name": "Oregon"
      }, {
        "name": "Pennsylvania"
      }, {
        "name": "Rhode Island"
      }, {
        "name": "South Carolina"
      }, {
        "name": "South Dakota"
      }, {
        "name": "Tennessee"
      }, {
        "name": "Texas"
      }, {
        "name": "Utha"
      }, {
        "name": "Vermont"
      }, {
        "name": "Virginia"
      }, {
        "name": "Washington"
      }, {
        "name": "West Virginia"
      }, {
        "name": "Wisconsin"
      }, {
        "name": "Wyoming"
      }]
    }
  },
  props: [
    "categories"
  ],
  computed: {
    salaryNeeded() {
      if (this.selectedCity != null && !isNaN(this.selectedCity.index)) {
        return this.salary * this.selectedCity.index
      }

      return 0
    }
  }
}
</script>

<style>
.result-text {
  font-size: 1em;
  text-align: center;
}

.result-input {
  font-size: 1em;
  width: 10%;
  border: none;
  text-align: center;
}
</style>
