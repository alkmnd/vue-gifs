<template>
    <view class="header-container">
        <text class="header">Trending</text>
    </view>
</template>
<script>
  export default {
    name: 'header.vue'
  };
</script>
<style scoped>
    .header-container {
        background-color: rgba(0, 0, 0, 0.05);
        display: flex;
        justify-content: center;
        padding-top: 15px;
        padding-bottom: 15px;
        border-bottom-color: aquamarine;
        border-bottom-width: 1px;
        margin-top: 20px;
    }
    .header {
        font-size: 16px;
        color: black;
        opacity: 0.8;
        font-weight: 600;
        text-align: center;
    }
</style>