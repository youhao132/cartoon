<template>
    <div class="hot">
    <div class="text-container">
      <span class="text1">畅销热门</span>
      <span class="text2">物有所值的真香漫画</span>
    </div>
    <div class="gallery">
      <div class="comic">
        <img src="../assets/hot/hot (1).jpg" alt="漫画1" @click="goToRead(4)">
        <p>更衣人偶墜入愛河</p>
      </div>
      <div class="comic">
        <img src="../assets/hot/hot (2).jpg" alt="漫画2" @click="goToRead(5)">
        <p>終將成為妳</p>
      </div>
      <div class="comic">
        <img src="../assets/hot/hot (3).jpg" alt="漫画3" @click="goToRead(6)">
        <p>鏈鋸人</p>
      </div>
      <div class="comic">
        <img src="../assets/hot/hot (4).jpg" alt="漫画4" @click="goToRead(7)">
        <p>工作細胞</p>
      </div>
      <div class="comic">
        <img src="../assets/hot/hot (5).jpg" alt="漫画5" @click="goToRead(8)">
        <p>間諜家家酒</p>
      </div>
    </div>
  </div>
</template>

<script >
export default{
  methods:{
    goToRead(comicId){
      this.$router.push({ name: 'read', params: { id: comicId, chapterId: 1 } });
    },
  },
}
</script>

<style scoped>
.hot {
  background-color: rgb(237, 243, 245);
  display: flex; /* 启用 Flexbox */
  flex-direction: column; /* 纵向排列 */
  align-items: flex-start; /* 左对齐 */
  padding: 20px; /* 增加内边距 */
}

.text-container {
  display: flex; /* 启用 Flexbox */
  flex-direction: row; /* 横向排列 */
  align-items: center; /* 垂直居中对齐 */
  margin-bottom: 20px; /* 底部间距 */
}

.text1 {
  margin-top: 50px;
  margin-left: 150px;
  font-size: 40px; /* 字体样式1 */
  color: black;
  margin-right: 10px; /* 添加间距 */
}

.text2 {
  margin-top: 75px;
  font-size: 20px; /* 字体样式2 */
  color: rgb(130, 127, 127);
}
.gallery {
  display: flex; /* 使用flex布局 */
  justify-content: space-around; /* 平均分配空间 */
  padding-left: 100px; /* 去掉默认内边距 */
  flex-wrap: wrap; /* 支持换行 */
  margin: 20px; /* 外边距 */
}

.comic {
  text-align: center; /* 文本居中 */
  margin: 10px; /* 每个漫画的外边距 */
}

.comic img {
  max-width: 100%; /* 图片自适应宽度 */
  height: auto; /* 保持图片比例 */
  border-radius: 8px; /* 图片边角圆润 */
}
</style>