<template>
    <section class="right-container">
        <div class="player-wrap">
            <Player></Player>
        </div>
        <div class="track-wrap">
            <TrackList></TrackList>
        </div>
    </section>
</template>
<script setup>
import Player from '@/components/Player/index.vue'
import TrackList from '@/components/TrackList/index.vue'
</script>
<style lang="scss" scoped>
    .right-container{
        height: 100%;
        display: flex;
        flex-direction: column;
        .player-wrap{
            flex: 0 0 550px;
            border-bottom:2px solid #151515;
        }
        .track-wrap{
            flex: 1;
        }
    }
</style>