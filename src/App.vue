<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <h1>multi-range-slider-vue demo</h1>
    <div class="multi-range-slider-container">
      <MultiRangeSlider />
    </div>
    <div class="multi-range-slider-container">
      <MultiRangeSlider
        :min="barMin"
        :max="barMax"
        :minValue="barMinValue"
        :maxValue="barMaxValue"
        :step="10"
        @input="UpdateValues"
      />
    </div>
    <div>
      <br />
      minValue={{ barMinValue }}
      <br />
      maxValue={{ barMaxValue }}
    </div>
  </div>
</template>

<script>
import MultiRangeSlider from "multi-range-slider-vue";

export default {
  name: "App",
  components: {
    MultiRangeSlider
  },
  data() {
    return { barMin: 0, barMax: 100, barMinValue: 10, barMaxValue: 90 };
  },
  methods: {
    UpdateValues(e) {
      this.barMinValue = e.minValue;
      this.barMaxValue = e.maxValue;
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.multi-range-slider-container {
  max-width: 500px;
  margin: 50px auto;
}
</style>
