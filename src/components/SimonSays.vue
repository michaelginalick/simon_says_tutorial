<template>
  <div id="game">

    <div class="red"></div>
    <div class="blue"></div>
    <div class="yellow"></div>
    <div class="green"></div>
  </div>

</template>

<script>
export default {
  name: 'SimonSays',
  data () {
    return {
    }
  },
  computed: {

  },
  methods: {
  }
}
</script>

<style scoped>
#game{
  margin: auto;
  width: 50%;
  padding: 10px;
}
.red {
  float:left;
  position: relative;
  width: 35%;
  padding-bottom: 30%;
  margin:1.66%;
  background-position:center center;
  background-repeat:no-repeat;
  background-color: #B20000;
}
.blue {
  float:left;
  position: relative;
  width: 35%;
  padding-bottom: 30%;
  margin:1.66%;
  background-position:center center;
  background-repeat:no-repeat;
  background-color: #2100B2;
}
.yellow {
  float:left;
  position: relative;
  width: 35%;
  padding-bottom: 30%;
  margin:1.66%;
  background-position:center center;
  background-repeat:no-repeat;
  background-color: #CCCC00;
}
.green {
  float:left;
  position: relative;
  width: 35%;
  padding-bottom: 30%;
  margin:1.66%;
  background-position:center center;
  background-repeat:no-repeat;
  background-color: #006400;
}
</style>