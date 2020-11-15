<template>
  <div class="main">
    <table>
      <tbody>
      <tr>
        <td colSpan="4">
          <input :readOnly="true"
                 :value="display"
          ></td>
      </tr>
      <tr>
        <td>
          <CalcButton num="7" @onClickCalcButton="onClickCalcButton"/>
        </td>
        <td>
          <CalcButton num="8" @onClickCalcButton="onClickCalcButton"/>
        </td>
        <td>
          <CalcButton num="9" @onClickCalcButton="onClickCalcButton"/>
        </td>
        <td>
          <CalcButton num="+" @onClickCalcButton="onClickCalcButton"/>
        </td>
      </tr>
      <tr>
        <td>
          <CalcButton num="4" @onClickCalcButton="onClickCalcButton"/>
        </td>
        <td>
          <CalcButton num="5" @onClickCalcButton="onClickCalcButton"/>
        </td>
        <td>
          <CalcButton num="6" @onClickCalcButton="onClickCalcButton"/>
        </td>
        <td>
          <CalcButton num="-" @onClickCalcButton="onClickCalcButton"/>
        </td>
      </tr>
      <tr>
        <td>
          <CalcButton num="1" @onClickCalcButton="onClickCalcButton"/>
        </td>
        <td>
          <CalcButton num="2" @onClickCalcButton="onClickCalcButton"/>
        </td>
        <td>
          <CalcButton num="3" @onClickCalcButton="onClickCalcButton"/>
        </td>
        <td>
          <CalcButton num="*" @onClickCalcButton="onClickCalcButton"/>
        </td>
      </tr>
      <tr>
        <td>
          <CalcButton num="0" @onClickCalcButton="onClickCalcButton"/>
        </td>
        <td>
          <CalcButton num="." @onClickCalcButton="onClickCalcButton"/>
        </td>
        <td>
          <CalcButton num="=" @onClickCalcButton="onClickCalcButton"/>
        </td>
        <td>
          <CalcButton num="/" @onClickCalcButton="onClickCalcButton"/>
        </td>
      </tr>
      <tr>
        <td colSpan="4">
          <CalcButton num="clear" @onClickCalcButton="onClickCalcButton"/>
        </td>
      </tr>
      </tbody>
    </table>
  </div>
</template>

<script>

import CalcButton from "@/components/CalcButton";

export default {
  name: 'Calc',
  components: {
    CalcButton
  },
  data: () => ({
    display: ''
  }),
  methods: {
    onClickCalcButton(num) {
      switch (num) {
        case "clear":
          this.setDisplay(0)
          break;
        case "+":
          this.setDisplay(this.display + "+")
          break
        case "=":
          this.setDisplay(eval(this.display).toString())
          break
        default:
          this.setDisplay(this.display + num)
      }
    },
    setDisplay(val) {
      this.display = val
    },
  },
  props: []
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
input {
  width: 100%;
  height: 30px;
  padding: 0;
  margin: 0
}

.main {
  left: calc(50% - 178px / 2);
  position: relative;
}
</style>
