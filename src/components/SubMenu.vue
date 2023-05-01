<template>
    <section class="sub-menu-content">
        <div class="menu-header">{{ title }}</div>
        <slot></slot>
    </section>
</template>
<script setup>
const prop = defineProps({
  title:{
    type:String,
    default:''
  }
})
</script>
<style lang="scss" scoped>
.sub-menu-content{
    color: #ffffff;
    .menu-header{
        height: 40px;
        line-height: 40px;
        padding-left: 10px;
        border-bottom: 1px solid #72727266;
    }
}
</style>