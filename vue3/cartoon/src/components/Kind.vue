<template>
    <div class="kind">
      <ul class="kind-links">
        <li><router-link to="/">热血</router-link></li>
        <li><router-link to="/">古风</router-link></li>
        <li><router-link to="/">玄幻</router-link></li>
        <li><router-link to="/">悬疑</router-link></li>
        <li><router-link to="/">都市</router-link></li>
        <li><router-link to="/">历史</router-link></li>
        <li><router-link to="/">架空</router-link></li>
        <li><router-link to="/">西幻</router-link></li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    name: 'KindNav',
  };
  </script>
  
  <style scoped>
  .kind {
    background-color: black;
    padding: 10px; /* 内边距 */
  }
  
  .kind-links {
    list-style-type: none; /* 去掉默认列表样式 */
    display: flex; /* 使用flex布局 */
    justify-content: space-around; /* 平均分配空间 */
    padding: 0; /* 去掉默认内边距 */
  }
  
  .kind-links li {
    margin: 0 15px; /* 每个链接之间的间距 */
  }
  
  .kind-links a {
    text-decoration: none; /* 去掉下划线 */
    color: white;
    font-weight: bold; /* 加粗字体 */
  }
  
  .kind-links a:hover {
    color: #0056b3; /* 悬停时的颜色变化 */
  }
  </style>
  