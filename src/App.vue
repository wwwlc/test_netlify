<template>
  <div class="waterfall-container">
    <Waterfall :list="list" :breakpoints="breakpoints">
      <template #default="{ url }">
        <div class="card">
          <LazyImg :url="getImg(url)" />
          <p class="text">{{item}}, {{ url }}kkkkkk</p>
        </div>
      </template>
    </Waterfall>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { Waterfall, LazyImg } from "vue-waterfall-plugin-next";
import "vue-waterfall-plugin-next/dist/style.css";

const list = ref([
  {
    src: "/img/dl.png", // 使用 require 引入图片
  },
  {
    src: "/img/hd.png", // 使用 require 引入图片
  },
  {
    src: "/img/dl.png", // 使用 require 引入图片
  },
  {
    src: "/img/hd.png", // 使用 require 引入图片
  },
  {
    src: "/img/dl.png", // 使用 require 引入图片
  },
  {
    src: "/img/hd.png", // 使用 require 引入图片
  },
  {
    src: "/img/dl.png", // 使用 require 引入图片
  },
  {
    src: "/img/hd.png", // 使用 require 引入图片
  },
  {
    src: "/img/dl.png", // 使用 require 引入图片
  },
  {
    src: "/img/hd.png", // 使用 require 引入图片
  },
]);
function getImg(url) {
  return new URL(url, import.meta.url);
}
const breakpoints = ref({
  3000: {
    rowPerView: 8,
  },
  1800: {
    rowPerView: 6,
  },
  1200: {
    rowPerView: 4,
  },
  500: {
    rowPerView: 2,
  },
});
</script>

<style scoped>
.waterfall-container {
  margin: 0;
  padding: 0;
}

.card_img {
  width: 100px;
  height: 100px;
  border: 1px solid red;
  border-radius: 5px;
}
</style>
