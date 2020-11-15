<template>
  <button @click="clickButton">{{ num }}</button>
</template>

<script>
export default {
  name: "CalcButton",
  props: [
      'num'
  ],
  methods: {
    clickButton() {
      this.$emit('onClickCalcButton', this.num)
    }
  }
}
</script>

<style scoped>
  button {
    height: 40px;
    width: 40px;
  }
</style>