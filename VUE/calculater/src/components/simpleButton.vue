<template>
  <div>
    <button class="signs" @click="plus">+</button>
    <button class="signs" @click="minus">-</button>
    <button class="signs" @click="multi">*</button>
    <button class="signs" @click="divi">/</button>
    <button class="res" @click="result">=</button>
  </div>
</template>

<script>
export default {
  emits: [
    "number-plus",
    "number-minus",
    "number-multi",
    "number-divi",
    "result",
  ],

  components: {},
  data() {
    return {
    };
  },

  methods: {
    plus() {
      this.$emit("number-plus");
    },
    minus() {
      this.$emit("number-minus");
    },
    multi() {
      this.$emit("number-multi");
    },
    divi() {
      this.$emit("number-divi");
    },
    result() {
      this.$emit("result");
    },
  },
};
</script>

<style>
body {
  font-family: monospace;
}
.signs {
  font-size: 20px;
  padding: 20px 55px 20px 55px;
  transition: 0.3s;
}

.res {
  font-size: 20px;
  padding: 20px 300px 20px 300px;
  margin-top: 1rem;
  transition: 0.3s;
}

button {
  box-shadow: 5px 5px 10px grey;
}

.signs:hover {
  background-color: #2c3e50;
  color: white;
  font-size: 1.5rem;
}

.res:hover {
  background-color: #2c3e50;
  color: white;
  font-size: 1.5rem;
}
</style>
