<template>
  <div >
  1.在Vue.js项目中，你正在开发一个组件，该组件包含两个子元素（.container和.content），要求如下：
1..container元素是一个具有固定宽度且自适应高度的居中容器，其背景颜色为浅灰色。当浏览器窗口尺寸改变时，容器的高度需要保持与内容区域（.content）相同，但不超过屏幕高度的80%。
2..content元素应当在其父元素.container内部水平垂直居中，并且内容自适应高度。同时，.content区域的高度需要根据内部动态内容实时更新，并且在高度变化时有一个平滑过渡效果。
<div class="container">
    <div class="content">

      {{ dynamicContent }}

    </div>
  </div>
</div>
  
</template>

<script>
export default {
  data() {
    return {
      dynamicContent: '初始文本',
    };
  },
  mounted() {
    // 假设这是一个从API获取数据或其他方式动态更新内容的函数
    this.updateContent();
  },
  methods: {
    updateContent() {
      // 模拟异步更新内容
      setTimeout(() => {
        this.dynamicContent = '更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本更新后的文本';
      }, 2000);

      // 如果有其他内容更新，继续在这里添加逻辑
    },
  },
};
</script>

<style scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #f0f0f0; /* 浅灰色背景 */
  width: 100%; /* 固定宽度，也可以设置为固定的px值 */
  max-height: 80vh; /* 不超过屏幕高度的80% */
  overflow: auto; /* 如果内容过长，提供滚动 */
}

.content {
  /* 用于垂直居中 */
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  width: 100%; /* 宽度根据父容器调整 */
  transition: height 0.3s ease; /* 高度变化时的平滑过渡效果 */
}
</style>