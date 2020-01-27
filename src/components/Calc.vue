<template>
  <div class="parent">
    <div class="display">{{disp}}</div>
    <div v-on:click="disp = ''" class="btn">C</div>
    <div v-on:click="round()" class="btn">_</div>
    <div v-on:click="percent()" class="btn">%</div>
    <div v-on:click="disp += '÷'" class="btn operator">÷</div>
    <div v-on:click="disp += 7" class="btn">7</div>
    <div v-on:click="disp += 8" class="btn">8</div>
    <div v-on:click="disp += 9" class="btn">9</div>
    <div v-on:click="disp += 'X'" class="btn operator">X</div>
    <div v-on:click="disp += 4" class="btn">4</div>
    <div v-on:click="disp += 5" class="btn">5</div>
    <div v-on:click="disp += 6" class="btn">6</div>
    <div v-on:click="disp += '-'" class="btn operator">-</div>
    <div v-on:click="disp += 1" class="btn">1</div>
    <div v-on:click="disp += 2" class="btn">2</div>
    <div v-on:click="disp += 3" class="btn">3</div>
    <div v-on:click="disp += '+'" class="btn operator">+</div>
    <div v-on:click="disp += 0" class="btn zero">0</div>
    <div v-on:click="disp += '.'" class="btn">.</div>
    <div v-on:click="equals()" class="btn operator">=</div>
  </div>
</template>

<script>
export default {
  name: "Calc",
  data() {
    return {
      disp: "0"
    };
  },
  methods: {
    equals() {
      console.log(this.disp.replace(/÷/g, '/').replace(/X/g, '*'))
      this.disp = eval(this.disp.replace(/÷/g, '/').replace(/X/g, '*'))
    },
    percent() {
      this.disp = this.disp * 100 + '%'
    },
    round() {
      this.disp = Math.round(this.disp)
    }
  },
};
</script>

<style scoped>
.parent {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: 1fr;
  width: 500px;
  height: 500px;
  position: relative;
  margin: auto;
}
.display {
  grid-area: 1 / 1 / 2 / 5;
  text-align: right;
  font-size: 60px;
  overflow-x: auto;
  overflow-y: hidden;
  background: #474a51;
  color: white;
  border-top: 1px solid black;
  border-left: 1px solid black;
  border-right: 1px solid black;
}
.btn {
  border: 1px solid black;
  background: #E0E0E0;
  padding: auto;
  text-align: center;
  padding-top: 20px;
  font-size: 32px;
}
.operator {
  background: #F29445;
}
.zero {
  grid-area: 6 / 1 / 6 / 3;
  text-align: right;
  padding-right: 55px
}
::-webkit-scrollbar {
  width: 11px;
}
body {
  scrollbar-width: thin;
  scrollbar-color: var(--thumbBG) var(--scrollbarBG);
}
::-webkit-scrollbar-track {
  background: var(--scrollbarBG);
}
::-webkit-scrollbar-thumb {
  background-color: var(--thumbBG) ;
  border-radius: 6px;
  border: 3px solid var(--scrollbarBG);
}
</style>
