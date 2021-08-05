<template>
  <div class='hello'>
    <div @click="initializeGame"  class="flex" >
      <!-- <a href="#1"  class="btn">Click Here to Stars Game!</a> -->
    </div>
    <ion-phaser
      :game.prop='game'
      :initialize.prop='initialize'
    />
  </div>
</template>

<script>
import Phaser from "phaser";

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      initialize: true,
      game: {
        width: '100%',
        height: '100%',
        type: Phaser.AUTO,
        scene: {
          init() {
          },
          preload() {
            this.load.image('sky', 'src/assets/sky.png');
            this.load.image('ground', 'assets/platform.png');
            this.load.image('star', 'assets/star.png');
            this.load.image('bomb', 'assets/bomb.png');
            this.load.spritesheet('dude', 
                'assets/dude.png',
                { frameWidth: 32, frameHeight: 48 }
            );

          },
          create() {

            console.log(this)

            this.add.image(400, 300, 'sky');
          },
          update() {

          }
        }
      }
    };
  },
  methods: {
    initializeGame() {
      this.initialize = true;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
