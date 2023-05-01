<template>
    <section class="left-container">
        <div class="menu-wrap">
            <Menu :menuList="menuList"></Menu>
        </div>
        <div class="sub-menu-wrap">
            <SubMenu title="视频编辑"></SubMenu>
        </div>
    </section>
</template>
<script setup>
import Menu from "@/components/Menu.vue"
import SubMenu from "../../components/SubMenu.vue";
const menuList = [
    {id:1,name:'视频'},
    {id:2,name:'字幕'},
    {id:3,name:'贴图'},
]
</script>
<style lang="scss" scoped>
.left-container{
    height: 100%;
    display: flex;
    border-right:2px solid #151515;
    .menu-wrap{
        border-right: 2px solid #151515;
    }
    .sub-menu-wrap{
        width: calc(100% - 80px);
    }
}

</style>