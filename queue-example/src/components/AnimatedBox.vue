<template>
  <div class="box"></div>
</template>

<script>
import Queue from "../data-structures/Queue";
import { gsap} from 'gsap';
export default {
  mounted: function() {
      this.animationQueue.enqueue({x:200, y:200, duration:2, onComplete: this.playNextAnimation})
      this.animationQueue.enqueue({backgroundColor:'red', rotate:25, duration:3, onComplete: this.playNextAnimation})
  
  },
  data: function() {
    return {
      animationQueue: new Queue()
    };
  },
  methods:{
      playNextAnimation:function(){
          // if there is any animation left
          if (this.animationQueue.peek()) {
              let nextAnimation = this.animationQueue.dequeue();
              gsap.to(this.$el, nextAnimation)
          }
      }
  }
};
</script>

<style scoped>
.box {
  width: 50px;
  height: 50px;
  border: 1px solid black;
}
</style>
