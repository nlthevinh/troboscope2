<template>
  <div :style="{backgroundColor: bgColor}" id="app">
    <button @click="start()">Clic</button>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'app',
  components: {
    HelloWorld,
  },
  data() {
     return {
        etat: false,
        listeColors:["red", "yellow", "green", "blue"],
        bgColor:"white",
        x: null,
        i:3,
      } 
  },
  methods: {
    strombo() {
        if (this.i == -1) {
          this.i = 3;
        }
        this.bgColor = this.listeColors[this.i];
        this.i--;
      },
    start() {
    
      if (this.etat == true) {
        this.etat = false;
        clearInterval(this.x);
      } else if (this.etat == false) {
        this.etat = true;
        this.x = setInterval(this.strombo, 50);
      }
    },
  }
};


</script>

<style>
div {
  position:fixed;
  right:0;
  left:0;
  top:0;
  bottom:0;
}
</style>