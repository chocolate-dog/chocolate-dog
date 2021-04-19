<template>
  <div class="w-number">
    <div class="prev" :class="{ dis: inputValue == min }" @click="prev">-</div>
    <input type="number" class="inputNum" v-model="inputValue" />
    <div class="next" :class="{ dis: inputValue == max }" @click="next">+</div>
  </div>
</template>
<script>
export default {
  props: {
    value: Number,
    min: [String, Number],
    max: [String, Number]
  },
  data() {
    return {
      num: 1,
      inputValue: this.value
    };
  },
  methods: {
    handleChange(value) {
      console.log(value);
    },
    prev() {
      if (this.min == this.inputValue) {
        return;
      }
      this.inputValue--;
    },
    next() {
      if (this.max == this.inputValue) {
        return;
      }
      // console.log(1212)
      this.inputValue++;
    }
  }
};
</script>
<style scoped>
input[type="number"] {
  -moz-appearance: textfield;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
.w-number {
  width: 180px;
  height: 40px;
  border: 1px solid #ccc;
  border-radius: 4px;
  display: flex;
}
.dis {
  color: #ccc;
  cursor: not-allowed;
}
.prev{
  border-right: 1px solid #ccc;
}
.next{
  border-left: 1px solid #ccc;
}
.prev,
.next {
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.inputNum {
  width: 100px;
  text-align: center;
  outline: none;
  border: none;
}
</style>