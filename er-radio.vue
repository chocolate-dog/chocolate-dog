<template>
  <div class="er-radio">
    <div
      :class="{
        radio: true,
        'radio-after': label==value
      }"
      @click="radioEvent"></div>
    <div>
      <slot></slot>
    </div>
  </div>
</template>
<script>
export default {
    props:{
        label:[String,Number],
        value:[String,Number]
    },
  data() {
    return {
      status: false
    };
  },
  methods:{
      radioEvent(){
          this.$emit('input',this.label)
      }
  }
};
</script>
<style scoped>
.er-radio {
  display: flex;
}
.radio {
  width: 14px;
  height: 14px;
  border-radius: 50%;
  border: 1px solid rgb(177, 177, 177);
}
.radio-after:after {
  content: "";
  width: 4px;
  height: 4px;
  border-radius: 50%;
  border: 5px solid #333;
  display: block;
}
</style>