<template>
  <div class="er-slider">
    <div class="slider">
      <div
        class="slider1" :style="{
          width: (this.value / 100 * 600 )+ 'px'
        }"
      ></div>
      <div
        class="slider2" :style="{
          left:((this.value / 100) * 600 > 22? 
          (this.value / 100) * 600 - 7
              : 0) + 'px'
        }"
      @click="press"></div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    value: Number
  },
  methods: {
    press(e){
      console.log(e)
      // console.log(offsetLeft)
      // console.log(e.pageX)
      
    },
  }
};
</script>
<style scoped>
.slider {
  margin: 100px auto;
  width: 600px;
  height: 8px;
  background-color: white;
  border-radius: 4px;
  border: 1px solid rgb(78, 115, 175);
}
.slider1 {
  width: 300px;
  height: 8px;
  background-color: rgb(78, 115, 175);
  border-radius: 4px;
}
.slider2 {
  height: 14px;
  width: 14px;
  border-radius: 50%;
  border: 1px solid rgb(78, 115, 175);
  background-color: white;
  position: relative;
  bottom: 12px;
  left: 293px;
}
</style>