<template>
  <div :class="['header-container', 'flx-justify-between flx-align-center', { scrolled: isScrolled }]">
    <img src="@/assets/images/logo.svg" alt="" />
    <span>
      <a href="https://www.linglong.space/" target="_blank">如意玲珑官网</a>
      <a href="https://github.com/OpenAtom-Linyaps/sig-linyaps-packing-sig" target="_blank">应用投递</a>
    </span>
  </div>
</template>
<script setup lang="ts">
import { ref, onMounted, onUnmounted } from "vue";

const isScrolled = ref(false);

// 处理滚动事件
const handleScroll = () => {
  isScrolled.value = window.scrollY > 66; // 设置滚动阈值
};

// 组件挂载时添加事件监听器
onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

// 组件卸载时移除事件监听器
onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>
<style scoped lang="scss">
.header-container {
  position: fixed;
  top: 0;
  left: 0;
  padding: 0 var(--container-margin);
  width: 100%;
  height: 66px;
  opacity: 1;
  box-sizing: border-box;
  background: rgb(255 255 255 / 43%);
  z-index: 100;
  span {
    font-size: 12px;
    a {
      margin-left: 12px;
    }
  }

  &.scrolled {
    background-color: #fff; /* 滚动后背景色变为白色 */
    box-shadow: 0 2.33px 4.67px rgb(0 0 0 / 5%);
  }

  img {
    width: 120px;
  }
}
</style>
