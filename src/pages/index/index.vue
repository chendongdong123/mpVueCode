<template>
  <div class="indexContainer">
    <img v-if="isShow" class="index_img" :src="userInfo.avatarUrl" alt="" />
    <Button
      class="btn"
      v-if="!isShow"
      open-type="getUserInfo"
      @getuserinfo="getUserInfo"
      >获取信息</Button
    >
    <p class="userName">hello mpvue {{ userInfo.nickName }}</p>
    <div @tap="toDetail" class="goStudy">
      <p>开启小程序之旅</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      userInfo: {},
      isShow: false,
    };
  },
  onLoad() {
    console.log("---onLoad--");
  },
  beforeMount() {
    this.handelGetUserInfo();
  },
  methods: {
    handelGetUserInfo: function () {
      wx.getUserInfo({
        success: (data) => {
          this.userInfo = data.userInfo;
        },
        fail: (error) => {
          console.log(error);
        },
      });
    },
    getUserInfo: function (data) {
      if (data.mp.detail.rawData) {
        console.log("wo shifou");
        this.handelGetUserInfo();
        this.isShow = true;
      }
    },
    toDetail() {
      wx.navigateTo({
        url: "/pages/list/main",
      });
    },
  },
};
</script>

<style>
page {
  background: chartreuse;
}
.indexContainer {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.index_img {
  width: 200rpx;
  height: 200rpx;
  border-radius: 100rpx;
  margin: 100rpx 0;
}
.userName {
  font-size: 40rpx;
  font-weight: bold;
  margin: 100rpx 0;
}
.goStudy {
  width: 220rpx;
  height: 80rpx;
  border: 1px solid #eee;
  font-size: 24rpx;
  text-align: center;
  border-radius: 10rpx;
  line-height: 80rpx;
}
.btn {
  width: 300rpx;
  height: 300rpx;
  border-radius: 150rpx;
  margin: 50rpx 0;
  line-height: 300rpx;
  text-align: center;
  font-size: 26rpx;
}
</style>
