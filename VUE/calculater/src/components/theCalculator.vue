<template>
  <div class="parent">
    <h1>Simple Calculator</h1>
    <input type="text" class="inputCalc" v-model="numberFromInput" />
      <simple-button class="buttons"
        @number-plus="plus"
        @number-minus="minus"
        @number-multi="multi"
        @number-divi="divi"
        @result="result"
      ></simple-button>
  </div>
</template>
<script>
import SimpleButton from "./simpleButton.vue";

export default {
  emits: ["resultNumber"],
  name: "App",
  props: {
  },
  components: {
    SimpleButton,
  },
  data() {
    return {
      numberFromInput: '',
      operator: "",
      resultNumber: 0,
    };
  },

  methods: {
    plus() {
      this.numberFirst = this.numberFromInput;
      this.operator = "+";
      this.numberFromInput = '';
    },
    minus() {
      this.numberFirst = this.numberFromInput;
      this.operator = "-";
      this.numberFromInput = '';
    },
    multi() {
      this.numberFirst = this.numberFromInput;
      this.operator = "*";
      this.numberFromInput = '';
    },
    divi() {
      this.numberFirst = this.numberFromInput;
      this.operator = "/";
      this.numberFromInput = '';
    },
    result() {
      this.numberSecond = this.numberFromInput;
      switch (this.operator) {
        case "+":
          this.resultNumber =
            parseInt(this.numberFirst) + parseInt(this.numberSecond);
            this.numberFromInput = this.resultNumber
          break;
        case "-":
          this.resultNumber =
            parseInt(this.numberFirst) - parseInt(this.numberSecond);
            this.numberFromInput = this.resultNumber
          break;
        case "*":
          this.resultNumber =
            parseInt(this.numberFirst) * parseInt(this.numberSecond);
            this.numberFromInput = this.resultNumber
          break;
        case "/":
          this.resultNumber =
            parseInt(this.numberFirst) / parseInt(this.numberSecond);
            this.numberFromInput = this.resultNumber
          break;
      }
    },
  },
};
</script>
<style>
.buttons {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
}
.parent {
  height:400px;
  box-shadow: 20px 20px 10px grey;
  margin: auto;
  width: 700px;
  background-color: lightgrey;
  padding-bottom: 10px;
}
.inputCalc {
  text-align: center;
  height: 50px;
  width: 610px;
  margin-bottom: 1rem;
  font-size: 30px;
}
h1 {
  font-size: 4rem;
  padding-top: 2rem;
}
</style>
