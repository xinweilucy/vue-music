<template>
  <div class="swiper-container">
    <div class="swiper-wrapper">
      <slot></slot>
    </div> <!-- 如果需要分页器 -->
    <div class="swiper-pagination"></div>
    <!-- 如果需要导航按钮 -->
    <!--<div class="swiper-button-prev"></div>-->
    <!--<div class="swiper-button-next"></div>-->
    <!-- 如果需要滚动条 -->
    <!--<div class="swiper-scrollbar"></div>-->
  </div>
</template>

<script type="text/ecmascript-6">
import 'swiper/dist/css/swiper.css'
import Swiper from 'swiper'
export default {
  name: 'Slider',
  mounted() {
    new Swiper('.swiper-container',
      { loop: true,
        autoplay: true,
        observer: true,
        observeParents: true,
        pagination: {
          el: '.swiper-pagination',
          clickable: true
        }
      })
  }
}
</script>

<style scoped>
.swiper-container { width: 100%; margin: 0; padding: 0; }
.swiper-wrapper { height: 200px; }
.swiper-slide img { max-width: 100%; }
.swiper-slide { text-align: center; background: #fff;
/* Center slide text vertically */
display: -webkit-box;
display: -ms-flexbox;
display: -webkit-flex;
display: flex;
-webkit-box-pack: center;
-ms-flex-pack: center;
-webkit-justify-content: center;
justify-content: center;
-webkit-box-align: center;
-ms-flex-align: center;
-webkit-align-items: center;
align-items: center; }
</style>