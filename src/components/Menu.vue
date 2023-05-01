<template>
    <section class="menu-content">
        <div class="menu-item" v-for="item in menuList" :key="item.id">
            <div class="inner-wrap">{{ item.name }}</div>
        </div>
    </section>
</template>
<script setup>
const props = defineProps({
  menuList:{
    type:Array,
    default:[]
  }
})

const emit = defineEmits(['change', 'delete'])
</script>
<style lang="scss" scoped>
    .menu-content{
        display: flex;
        flex-direction: column;
        height: 100%;
        width: 80px;
        .menu-item{
            width: 100%;
            height: 80px;
            font-size: 14px;
            color: #ffffff66;
            display: flex;
            justify-content: center;
            align-items: center;
            
            .inner-wrap{
                width:70px;
                height: 70px;
                border-radius: 5px;
                text-align: center;
                line-height: 70px;
                &:hover{
                    color: #ffffffe6;
                    background-color: #f0f4fc06;
                    cursor: pointer;
                }
            }
        }
    }
</style>