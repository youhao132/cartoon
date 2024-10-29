<template>
  <div class="header">
    <div class="part1">
      <img src="../assets/images.jpg" class="img1">
      <span class="part1-text">aa漫画</span>
    </div>
    <ul class="nav1">
      <li><router-link to="/">首页</router-link></li>
      <li><router-link to="/">分类</router-link></li>
      <li><router-link to="/">更新</router-link></li>
      <li><router-link to="/about">排行榜</router-link></li>
    </ul>
    <div class="part3">
      <div class="search-container">
        <input type="text" class="search-input" placeholder="搜索...">
        <button class="search-button">
          <el-icon><Search /></el-icon>
        </button>
      </div>
      <ul class="nav2">
        <li><router-link to="/">下载历史</router-link></li>
        <li><router-link to="/">历史</router-link></li>
        <li><router-link to="/">追漫</router-link></li>
        <li>
          <el-button type="primary">
            投稿<el-icon class="el-icon--right"><Upload /></el-icon>
          </el-button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
};
</script>

<style scoped>
.header {
  position: fixed; /* 固定 */
  height: 50px;
  top: 0;
  left: 0;
  width: 100%;
  background-color: #fff; /* 背景颜色 */
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1); /* 阴影效果 */
  z-index: 1000; /* 确保导航栏在其他元素之上 */
  display: flex; /* 使用Flexbox布局 */
  align-items: center; /* 垂直居中对齐 */
}

.part1{
  margin-left: 200px;
  display: flex;
  align-items: center;
}

.img1{
  padding-right: 10px;
  height: 30px;
  width: auto;
}

.part1-text{
  font-size: 15px;
}

.nav1{
  margin-left: 40px; 
  width: 300px;
  list-style-type: none; /* 去掉默认的列表样式 */
  padding: 0; /* 去掉内边距 */
  display: flex; /* 使用Flexbox布局 */
  justify-content: space-between; /* 在导航链接之间均匀分布 */
}

.header a {
  text-decoration: none; /* 去掉链接的下划线 */
  color: #333; /* 链接颜色 */
}

.part3{
  margin-left: 150px;
  display: flex;
  align-items: center;
}

.search-container {
    display: flex; /* 使用 Flexbox 布局 */
    align-items: center; /* 垂直居中 */
    border-radius: 20px; /* 圆角 */
    background-color: #f0f0f0; /* 灰色背景 */
    padding: 5px; /* 内边距 */
    max-width: 400px; /* 最大宽度 */
}

.search-input {
    border: none; /* 去掉边框 */
    background: transparent; /* 透明背景 */
    border-radius: 20px; /* 圆角 */
    outline: none; /* 去掉聚焦边框 */
}

.search-button {
    background: none; /* 去掉按钮背景 */
    border: none; /* 去掉边框 */
    cursor: pointer; /* 鼠标悬停变为手形 */
}

.search-button .el-icon-search {
    font-size: 20px; /* 图标大小 */
    color: #333; /* 图标颜色 */
}

.nav2{
  margin-top: 9px;
  margin-left: 40px; 
  width: 300px;
  list-style-type: none; /* 去掉默认的列表样式 */
  padding: 0; /* 去掉内边距 */
  display: flex; /* 使用Flexbox布局 */
  justify-content: space-between; /* 在导航链接之间均匀分布 */
}

</style>