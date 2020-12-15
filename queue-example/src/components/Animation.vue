<template>
    <div>
        <div>
            <button @click='play'>Play</button>
        </div>
        <AnimatedBox ref="box"/>
    </div>
</template>

<script>

import AnimatedBox from './AnimatedBox';
export default {
    components:{
        AnimatedBox
    },
    methods:{
        play:function(){
            this.$refs.box.playNextAnimation();
        }
    }
   
}
</script>

<style scoped>

</style>