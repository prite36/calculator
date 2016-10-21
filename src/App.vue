<template lang="html">
  <div class="">
    <button type="" name="button" @click="setNumber(1)">1</button>
    <button type="" name="button" @click="setNumber(2)">2</button>
    <button type="" name="button" @click="setNumber(3)">3</button>
    <button type="" name="button" @click="setNumber(4)">4</button>
    <button type="" name="button" @click="setNumber(5)">5</button>
    <button type="" name="button" @click="setNumber(6)">6</button>
    <button type="" name="button" @click="setNumber(7)">7</button>
    <button type="" name="button" @click="setNumber(8)">8</button>
    <button type="" name="button" @click="setNumber(9)">9</button>
    <button type="" name="button" @click="setNumber(0)">0</button>
    <button type="" name="button" @click="setOperate('+')">+</button>
    <button type="" name="button" @click="setOperate('-')">-</button>
    <button type="" name="button" @click="setOperate('*')">*</button>
    <button type="" name="button" @click="setOperate('/')">/</button>
    <button type="" name="button" @click="getResult()">=</button>
    <button type="" name="button" @click="reset()">C</button><br>
    {{number1}} {{operate}} {{number2}} = {{result}}
  </div>
</template>

<script>
export default {
  data () {
    return {
      number1: '',
      number2: '',
      operate: '',
      result: '',
      state: 0
    }
  },
  computed: {},
  mounted () {},
  methods: {
    setNumber: function (number) {
      if (this.state === 0) {
        this.number1 += number
      } else if (this.state === 1) {
        this.number2 += number
      }
    },
    setOperate: function (operate) {
      this.operate = operate
      this.state = 1
    },
    getResult: function () {
      if (this.operate === '+') {
        this.result = parseInt(this.number1) + parseInt(this.number2)
      }
      if (this.operate === '-') {
        this.result = parseInt(this.number1) - parseInt(this.number2)
      }
      if (this.operate === '*') {
        this.result = parseInt(this.number1) * parseInt(this.number2)
      }
      if (this.operate === '/') {
        this.result = parseInt(this.number1) / parseInt(this.number2)
      }
      this.state = 3
    },
    reset: function () {
      this.state = 0
      this.number1 = ''
      this.number2 = ''
      this.operate = ''
      this.result = ''
    }

  },
  components: {}
}
</script>

<style lang="css">
</style>
