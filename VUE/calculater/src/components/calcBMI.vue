<template>
  <div class="divBMI">
    <h1 class="h1BMI">Calculate BMI</h1>
    <div>
      <input type="text" class="inputBMI" v-model="numberSize" placeholder="Size in Centimeter" />
      <input type="text" class="inputBMI" v-model="numberWeight" placeholder="Weight in Kilogram" />
    </div>
    <button @click="bmiCalc" class="buttonBMI">Calculate BMI</button>
    <p class="output">{{ result }}</p>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      result: "",
      numberSize: "",
      numberWeight: "",
    };
  },

  methods: {
    bmiCalc() {
      this.result = this.numberWeight / ((this.numberSize /100) * (this.numberSize/100));
    },
  },
};
</script>

<style>
.inputBMI {
  padding: 10px 50px 10px 50px;
  margin-left: 1rem;
  margin-right: 1rem;
  text-align: center;
}

.divBMI {
  background-color: lightgrey;
  box-shadow: 20px 20px 10px grey;
  margin: auto;
  width: 700px;
  padding-bottom: 10px;
}

.h1BMI {
  font-size: 2rem;
}

.buttonBMI {
  font-size: 20px;
  padding: 20px 55px 20px 55px;
  transition: 0.3s;
  margin-top: 1rem;
}

.output {
  font-size: x-large;
  font-weight: bolder;
}
</style>
