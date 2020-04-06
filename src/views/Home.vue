<template>
  <div class="home">
    <div class="title">产品追溯</div>
    <van-divider :style="{ color: '#58727e', borderColor: '#58727e', padding: '0 16px' }">
      Product Traceability
    </van-divider>
    <div class="block">
      <van-button type="info" class="x-btn" @click="handleDownLoad('https://krtxplay1.setrtmp.com/live/SSSS-117846-FBDFC.m3u8')">东港基地</van-button>
    </div>
    <div class="block">
      <van-button type="info" class="x-btn" @click="handleDownLoad('https://krtxplay1.setrtmp.com/live/SSSS-117873-CEBBB.m3u8')">北票基地</van-button>
    </div>
    <div class="block">
      <van-button type="info" class="x-btn" @click="handleDownLoad('https://krtxplay1.setrtmp.com/live/SSSS-117873-CEBBB.m3u8')">喀左基地</van-button>
    </div>

    <transition name="van-slide-up">
      <div class="modal" v-show="visible" @click="visible = false">
        <div v-show="visible">
          <video class="video-layer" :src="currentUrl" controls @click.stop></video>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
import Vue from 'vue'
import { Button, Divider, Overlay } from 'vant'
import 'vant/lib/button/style'
Vue.use(Button).use(Divider).use(Overlay)
export default {
  name: 'Home',
  data () {
    return {
      visible: false,
      currentUrl: ''
    }
  },
  methods: {
    handleDownLoad (url) {
      this.currentUrl = url
      this.visible = true
    }
  }
}
</script>

<style scoped lang="scss">
  .title {
    color: #58727e;
    font-size: 24px;
    font-weight: bold;
    padding: 10px 0;
    margin-top: 20px;
  }
  .block {
    margin-top: 60px;
  }
  .x-btn {
    width: 120px;
  }
  .video-layer {
    width: 90vw;
  }
  .modal {
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,.5);
  }
  .modal > div {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>
