<template>
    <section class="track-list-container">
        <div class="track-options-container">
            <TrackOptions></TrackOptions>
        </div>
        <div class="track-container">
            <div class="track-head-container">
                <TrackHead></TrackHead>
            </div>
            <div class="track-line-container">
                <div class="track-time-line-container">
                    <TrackTimeLine></TrackTimeLine>
                </div>
            </div>
        </div>
    </section>
</template>
<script setup>
import TrackOptions from './TrackOptions.vue';
import TrackHead from './TrackHead.vue';
import TrackTimeLine from './TrackTimeLine.vue';
</script>
<style lang="scss" scoped>
.track-list-container{
    position: relative;
    width:100%;
    height: 100%;
    .track-options-container{
            border-bottom: 1px solid #383838;
        }
    .track-container{
        position: absolute;
        top:50px;
        height: calc(100% - 50px);
        width: 100%;
        display: flex;
        .track-head-container{
            width: 60px;
            height: 100%;
            border-right: 1px solid #383838;
        }
        .track-line-container{
            position: absolute;
            overflow: auto;
            left: 60px;
            right: 0;
            top: 0;
            bottom: 0;
        }
    }
}
</style>