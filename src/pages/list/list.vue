<template>
  <div class="listContail">
    <swiper
      indicator-dots
      indicator-color="pink"
      indicator-active-color="green"
    >
      <swiper-item>
        <img src="../../static/images/index/timg.jpeg" alt="" />
      </swiper-item>
      <swiper-item>
        <img src="../../static/images/index/timg (1).jpeg" alt="" />
      </swiper-item>
      <swiper-item>
        <img src="../../static/images/index/timg (2).jpeg" alt="" />
      </swiper-item>
      <swiper-item>
        <img src="../../static/images/index/timg (3).jpeg" alt="" />
      </swiper-item>
      <swiper-item>
        <img src="../../static/images/index/timg (4).jpeg" alt="" />
      </swiper-item>
    </swiper>
    <listTemplate />
  </div>
</template>

<script>
import listTemplate from "../list_template/list_template";
export default {
  data() {},
  components: {
    listTemplate,
  },
};
</script>

<style>
.listContail swiper {
  width: 100%;
  height: 400rpx;
}
.listContail swiper img {
  width: 100%;
  height: 100%;
}
</style>
