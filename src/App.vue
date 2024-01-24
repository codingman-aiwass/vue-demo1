<template>
  <div>
<!--    头部-->
  <Header/>
<!--    主体-->


    <div style="display: flex">
<!--      侧边栏-->
      <Aside/>
<!--      内容区域-->

      <router-view/>
    </div>

  </div>

</template>

<style>

</style>
<script>
import Header from "@/components/Header.vue";
import Aside from "@/components/Aside.vue";

export default {
  name:"Layout",
  components:{
    Header,
    Aside
  }
}
const debounce = (fn, delay) => {
  let timer = null;
  return function () {
    let context = this;
    let args = arguments;
    clearTimeout(timer);
    timer = setTimeout(function () {
      fn.apply(context, args);
    }, delay);
  }
}

const _ResizeObserver = window.ResizeObserver;
window.ResizeObserver = class ResizeObserver extends _ResizeObserver {
  constructor(callback) {
    callback = debounce(callback, 16);
    super(callback);
  }
}

</script>