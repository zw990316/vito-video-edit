<template>
    <section class="trigger-content">
        <div class="time-wrap">
            <span>{{ curTime }}/{{ totalTime }}</span>
        </div>
        <div class="pause-wrap">
            <el-icon size="25" color="#fffff66" style="cursor:pointer">
                <svg v-if="true" viewBox="0 0 1024 1024" xmlns="http://www.w3.org/2000/svg" data-v-ea893728=""><path fill="currentColor" d="M512 64a448 448 0 1 1 0 896 448 448 0 0 1 0-896zm0 832a384 384 0 0 0 0-768 384 384 0 0 0 0 768zm-48-247.616L668.608 512 464 375.616v272.768zm10.624-342.656 249.472 166.336a48 48 0 0 1 0 79.872L474.624 718.272A48 48 0 0 1 400 678.336V345.6a48 48 0 0 1 74.624-39.936z"></path></svg>
                <svg v-else viewBox="0 0 1024 1024" xmlns="http://www.w3.org/2000/svg" data-v-ea893728=""><path fill="currentColor" d="M512 64a448 448 0 1 1 0 896 448 448 0 0 1 0-896zm0 832a384 384 0 0 0 0-768 384 384 0 0 0 0 768zm-96-544q32 0 32 32v256q0 32-32 32t-32-32V384q0-32 32-32zm192 0q32 0 32 32v256q0 32-32 32t-32-32V384q0-32 32-32z"></path></svg>
            </el-icon>
        </div>
    </section>
</template>
<script setup>
const props = defineProps({
    totalTime:{
        type:String,
        default:'00:00:00'
    },
    curTime:{
        type:String,
        default:'00:00:00'
    }
})
</script>
<style lang="scss" scoped>
    .trigger-content{
        justify-content: center;
        box-sizing: border-box;
        padding: 12px;
        width: 100%;
        height: 50px;
        .time-wrap{
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
        }
        .pause-wrap{
            display: flex;
            width: 100%;
            height: 100%;
            justify-content: center;
            align-items: center;
        }
    }
</style>
