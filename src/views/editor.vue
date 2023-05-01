<template>
    <section class="main">
        <TopBar></TopBar>
        <div class="editor-container">
            <div class="left-wrap">
                <LeftContainer></LeftContainer>
            </div>
            <div class="right-wrap">
                <RightContainer></RightContainer>
            </div>
        </div>
    </section>
</template>
<script setup>
import TopBar from '@/views/components/TopBar.vue';
import LeftContainer from './components/LeftContainer.vue';
import RightContainer from './components/RightContainer.vue';
</script>
<style lang="scss" scoped>
    .main{
        position:absolute;
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        .editor-container{
            display: flex;
            flex: 1 1 auto;
            min-height: 592px;
            .left-wrap{
                flex: 0 0 400px;
            }
            .right-wrap{
                flex: 1 0 800px;
            }
        }
    }
</style>