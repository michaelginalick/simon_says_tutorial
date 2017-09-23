<template>
  <div id="game">
    <div class="red" v-bind:class="{red_active: active.red === true}" v-on:click= "handleClick($event)"></div>
    <div class="blue" v-bind:class="{blue_active: active.blue === true}" v-on:click="handleClick($event)"></div>
    <div class="yellow" v-bind:class="{yellow_active: active.yellow === true}" v-on:click="handleClick($event)"></div>
    <div class="green" v-bind:class="{green_active: active.green === true}" v-on:click="handleClick($event)"></div>
  </div>

</template>

<script>
export default {
  name: 'SimonSays',
  data () {
    return {
      active:{
        red: false,
        blue: false,
        green: false,
        yellow: false,
      },

      hexCodes: {
        red: "#FF0000",
        blue: "#1e90ff",
        yellow: "#ffff00",
        green: "#32cd32"
      },
    }
  },
  computed: {

  },


  created() {
    const self = this
    self.startGame()
  },


  methods: {
    handleClick(target) {
    const self = this

    Object.keys(self.active).forEach(key => {
     if(target.currentTarget.className === key) {
       self.active[key] = true
      }
     })
    },


    startGame() {
      const self = this
      let i = 20

      setTimeout(function() {
        let redSquareHexCode = self.hexCodes.red

        self.setElementToTrue(redSquareHexCode)
        if (--i){
          self.startGame(i--)
        }
      }, 3000)
    },

    setElementToTrue(redSquareHexCode) {
      const self = this

      Object.entries(self.hexCodes).forEach(key => {
        if (key[1] == redSquareHexCode) {
          self.active[key[0]] = true
          self.toggleToFalse()
        }
      })
    },

    toggleToFalse(key) {
      const self = this

      setTimeout(function() {
        Object.entries(self.active).forEach(key => {
          self.active[key[0]] = false
        })
      }, 1000)
    }
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

.red_active {
  background-color: #FF0000;
}
.blue_active {
  background-color: #1e90ff;
}
.green_active {
  background-color: #32cd32;
}
.yellow_active {
  background-color: #ffff00;
}
</style>