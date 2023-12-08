<template>
  <view class="music-list">
    <!-- 搜索栏 -->
    <view class="search">
      <input type="text" placeholder="搜索歌单" />
      <button type="primary">搜索</button>
    </view>
    <!-- 歌单列表 -->
    <view class="list">
      <m-music-list-item
        v-for="(item, index) in musicList"
        :key="index"
        :name="item.name"
        :picUrl="item.picUrl"
        :pla…[omitted]
    </view>
  </view>
</template>

<script>
export default {
  // 数据和方法
};
</script>

<style scoped>
/* 样式 */
</style>
