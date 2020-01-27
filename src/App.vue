<template>
  <div id="app">
    <Header/>
    <Calc/>
  </div>
</template>

<script>
import Calc from './components/Calc.vue'
import Header from './components/Header'

export default {
  name: 'app',
  components: {
    Calc,
    Header
  }
}
</script>

<style>
html {
  font-family: 'Abel', sans-serif;
}
::-webkit-scrollbar {
  width: 8px; /* 1px wider than Lion. */
  /* This is more usable for users trying to click it. */
  background-color: rgba(0,0,0,0);
  -webkit-border-radius: 100px;
}
/* hover effect for both scrollbar area, and scrollbar 'thumb' */
::-webkit-scrollbar:hover {
  background-color: rgba(0, 0, 0, 0.09);
}
::-webkit-scrollbar-thumb {
  /* This is the EXACT color of Mac OS scrollbars. 
     Yes, I pulled out digital color meter */
  background: white;
  -webkit-border-radius: 100px;
}
::-webkit-scrollbar-thumb:active {
  background: rgba(0,0,0,0.61); /* Some darker color when you click it */
  -webkit-border-radius: 100px;
}
</style>
