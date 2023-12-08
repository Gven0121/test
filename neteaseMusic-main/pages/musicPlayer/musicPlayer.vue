<template>
  <view class="music-player">
	  
    <!-- 歌曲信息 -->
    <view class="info">
      <image class="pic" :src="currentSong.picUrl"></image>
      <view class="detail">
        <text class="name">{{ currentSong.name }}</text>
        <text class="singer">{{ currentSong.singer }}</text>
      </view>
    </view>
    <!-- 播放器控制 -->
   <view class="control">
      <button class="prev" @tap="handlePrev">
        <text class="iconfont icon-prev"></text>
      </button>
      <button class="play" @tap="handlePlay">
        <text class="iconfont" :class="{ 'icon-play': !isPlaying, 'icon-pause': isPlaying }"></text>
      </button>
      <button class="next" @tap="handleNext">
        <text class="iconfont icon-next"></text>
      </button>
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
export default {
  data() {
    return {
      currentSong: {
        picUrl: '歌曲封面图片路径',
        name: '歌曲名称',
        singer: '歌手名称'
      },
      isPlaying: false
    };
  },
  methods: {
    handlePrev() {
      // 播放上一首歌曲的逻辑
    },
    handlePlay() {
      this.isPlaying = !this.isPlaying;
      // 播放或暂停当前歌曲的逻辑
    },
    handleNext() {
      // 播放下一首歌曲的逻辑
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
  }
};
</script>

<style>
	.bottom-nav {
	  position: fixed;
	  bottom: 0;
	  left: 0;
	  width: 100%;
	  height: 50px;
	  background-color: #fff;
	  display: flex;
	  justify-content: space-around;
	  align-items: center;
	}
	.nav-item {
	  display: flex;
	  flex-direction: column;
	  align-items: center;
	}
	.nav-item text {
	  font-size: 12px;
	  margin-top: 4px;
	}
	.music-player {
	  display: flex;
	  flex-direction: column;
	  align-items: center;
	  justify-content: center;
	  height: 100vh;
	  background-color: #f5f5f5;
	}

	.info {
	  display: flex;
	  align-items: center;
	  margin-bottom: 20px;
	}

	.pic {
	  width: 100px;
	  height: 100px;
	  border-radius: 50%;
	  margin-right: 10px;
	}

	.detail {
	  display: flex;
	  flex-direction: column;
	}

	.name {
	  font-size: 18px;
	  font-weight: bold;
	}

	.singer {
	  font-size: 14px;
	  color: #888;
	}

	.control {
	  display: flex;
	  justify-content: center;
	  margin-bottom: 20px;
	}

	button {
	  background-color: transparent;
	  border: none;
	  cursor: pointer;
	}

	.iconfont {
	  font-size: 24px;
	}

	.prev {
	  margin-right: 20px;
	}

	.play {
	  margin: 0 20px;
	}

	.bottom-nav {
	  position: fixed;
	  bottom: 0;
	  left: 0;
	  width: 100%;
	  height: 50px;
	  background-color: #fff;
	  display: flex;
	  justify-content: space-around;
	  align-items: center;
	}

	.nav-item {
	  display: flex;
	  flex-direction: column;
	  align-items: center;
	}

	.nav-item text {
	  font-size: 12px;
	  margin-top: 4px;
	}
</style>
