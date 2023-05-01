<template>
    <div class="top-wrap">
        <div class="logo">Vito</div>
        <div class="title">视频编辑器</div>
        <div class="option">
            <el-button type="primary">导出</el-button>
        </div>
    </div>
</template>
<script setup>
</script>
<style lang="scss" scoped>
    .top-wrap{
        position: relative;
        display: flex;
        justify-content: space-between;
        align-items: center;
        text-align: center;
        color: #ffffff;
        height: 50px;
        box-sizing: border-box;
        padding: 10px 0;
        font-size: 14px;
        width: 100%;
        &::after{
            content: ' ';
            bottom: 0;
            background-color: #151515;
            height: 2px;
            width: 100%;
            position: absolute;
        }
        .logo{
            margin-left: 25px;
        }
        .option{
            margin-right: 10px;
        }
    }
</style>