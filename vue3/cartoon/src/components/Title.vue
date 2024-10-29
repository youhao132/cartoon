<template>
    <div class="title-wrapper">
      <div class="part1">
        <img src="../assets/images.jpg" class="img1">
        <span class="part1-text">aa漫画</span>
      </div>
      <div class="part2">
        <router-link to="/">首页</router-link>
      </div>
      <div class="part3">
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

</script>

<style scoped>
.title-wrapper{
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

.title-wrapper a {
  text-decoration: none; /* 去掉链接的下划线 */
  color: #333; /* 链接颜色 */
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

.part2{
    margin-left: 40px;
}

.part3{
  margin-left: 700px;
  display: flex;
  align-items: center;
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