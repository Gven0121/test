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
        :playCount="item.playCount"
        @tap="handleToDetail(item.id)"
      ></m-music-list-item>
    </view>
	<!-- 底部导航栏 -->
	<view class="bottom-nav">
	  <view class="nav-item" @tap="goToProfile">
	    <text class="iconfont icon-person"></text>
	    <text>我的</text>
	  </view>
	  <view class="nav-item" @tap="goToMusicList">
	    <text class="iconfont icon-music"></text>
	    <text>歌单</text>
	  </view>
	  <view class="nav-item" @tap="goToMusicPlayer">
	    <text class="iconfont icon-play"></text>
	    <text>播放</text>
	  </view>
	</view>
  </view>
</template>

<script>
	import MusicList from '../../components/MusicList/MusicList.vue'
	//import musichead from '../../components/musichead/musichead.vue'
	import { login } from '../../common/api.js'
	export default {
	  methods: {
		// ...
		handleToDetail(id) {
		  // 跳转到歌单详情页，参数为歌单 id
		},
		goToProfile() {
		      // 跳转到我的个人模块
			  uni.navigateTo({
			        url: '/pages/index/index'
			      });
		},
		goToMusicList() {
		      // 跳转到音乐歌单发现模块
			uni.navigateTo({
			    url: '/pages/musicList/musicList'
			});
		},
		goToMusicPlayer() {
		      // 跳转到音乐播放界面模块
			uni.navigateTo({
			    url: '/pages/musicPlayer/musicPlayer'
			});
		},
	  },
	};
	</script>

<style>
/* ... */
	.bottom-nav { position: fixed;bottom: 0;left: 0;width: 100%;height: 50px;background-color: #fff;display: flex;justify-content: space-around;align-items: center;}
	.nav-item {display: flex;flex-direction: column;align-items: center;}
	.nav-item text {font-size: 12px;margin-top: 4px;}
</style>
