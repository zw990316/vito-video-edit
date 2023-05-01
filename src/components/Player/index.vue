<template>
    <section class="player-content">
        <div class="title">播放器</div>
        <div class="canvas-wrap">
            <VideoPlayer></VideoPlayer>
        </div>
        
        <div class="video-trigger-wrap">
            <VideoTrigger></VideoTrigger>
        </div>
        
    </section>
</template>
<script setup>
import VideoPlayer from './VideoPlayer.vue';
import VideoTrigger from './VideoTrigger.vue';


</script>
<style lang="scss" scoped>
.player-content{
    position: relative;
    height: 100%;
    color: azure;
    .title{
        padding-left: 10px;
        font-size: 14px;
        height: 40px;
        line-height: 40px;
    }
    .canvas-wrap{
        box-sizing: border-box;
        height: calc(100% - 90px);
        overflow: hidden;
        padding: 10px;
    }
    .video-trigger-wrap{
        position: absolute;
        width: 100%;
        bottom: 0;
    }
}
</style>