<template>
  <div class="container">
    <h1>高度固定长列表渲染</h1>
    <virtual-recycle-scroller :items="list" />
    <h1>高度不固定长列表渲染</h1>
    <virtual-dynamic-scroller :items="list" />
    <h1>自己实现的长列表渲染</h1>
    <my-virtual-scroller :items="list" />
  </div>
</template>

<script>
import virtualRecycleScroller from "@/components/virtualRecycleScroller";
import virtualDynamicScroller from "@/components/virtualDynamicScroller.vue";
import myVirtualScroller from "@/components/myVirtualScroller";
// 模拟一个长列表
const list = [];
for (let i = 0; i < 10000; i++) {
  list.push({
    id: i,
    label: `virtual-list ${i}`,
  });
}

// // 模拟一个内容不同的列表项
// list[2].label = `virtual-scroller 前端 前端 前端 前端 前端 前端 前端
// 前端 前端 前端 前端 前端 前端 前端 前端 前端 前端 前端
// 前端 前端 前端 前端 前端 前端 前端 前端 前端 前端 `;

export default {
  components: {
    virtualRecycleScroller,
    virtualDynamicScroller,
    myVirtualScroller,
  },

  data() {
    return {
      list: list,
    };
  },
};
</script>

<style scoped>
.container {
  height: 300px;
  border: 1px solid #ccc;
}
</style>
