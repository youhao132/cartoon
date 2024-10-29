<template>
  <div class="ebook">
    <div class="read-wrapper">
      <div id="read"></div>
      <div class="mask">
        <div class="left" @click="prevPage"></div>
        <div class="center" @click="toggleTitleAndMenu"></div>
        <div class="right" @click="nextPage"></div>
      </div>  
    </div>
    <div class="all" v-show="show">
    <Title />
    <div class="bottom">
      <button class="prevbutton" @click="prev">
          <el-icon><ArrowLeftBold /></el-icon>
      </button>
      <button class="nextbutton" @click="next">
        <el-icon><ArrowRightBold /></el-icon>
      </button>
    </div>
    </div>
  </div>
</template>

<script>
import Epub from 'epubjs';
import Title from "../components/Title.vue"
export default {
  components:{
    Title,
  },

  data() {
    return {
      book: null,
      comicId: null,
      currentChapter: 1, 
      show:false,
    };
  },

  methods: {
    toggleTitleAndMenu(){
      this.show = !this.show
    },
    showEpub() {
      // 生成Book对象
      const DOWNLOAD_URL = `/${this.comicId}/${this.currentChapter}.epub`;
      this.book = new Epub(DOWNLOAD_URL)
      // 通过Book.renderTo生成Rendition对象
      this.rendition = this.book.renderTo('read', {
        width: window.innerWidth,
        height: window.innerHeight,
        method: 'default'
      })
      // 通过Rendtion.display渲染电子书
      this.rendition.display()
      console.log(DOWNLOAD_URL)
    },
    // 上一页
    prevPage() {
      if (this.rendition) {
        this.rendition.prev()
      }
    },
    // 下一页
    nextPage() {
      if (this.rendition) {
        this.rendition.next()
      }
    },
    prev() {
      this.currentChapter--
      this.$router.push({ name: 'read', params: { id: this.comicId, chapterId: this.currentChapter } });
    },
    next() {
      this.currentChapter++
      this.$router.push({ name: 'read', params: { id: this.comicId, chapterId: this.currentChapter } });
   },
  },

  created() {
    if (this.$route.params.id) {
      this.comicId = this.$route.params.id;
      this.currentChapter = this.$route.params.chapterId
    }
  },

  mounted() {
    this.showEpub();
  },
  watch: {
    '$route'(to, from) {
      // 路由变化时调用 this.$router.go(0)
      this.$router.go(0);
    }
  }
}
</script>

<style scoped>
.ebook {
  position: relative;
}

.mask {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 100;
  display: flex;
  width: 100%;
  height: 100%;
}

.left {
  flex: 1;
}

.center {
  flex: 1;
}

.right {
  flex:1;
}

.bottom{
  position: fixed; /* 固定 */
  height: 50px;
  bottom: 0;
  left: 0;
  width: 100%;
  background-color: #fff; /* 背景颜色 */
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1); /* 阴影效果 */
  z-index: 1000; /* 确保导航栏在其他元素之上 */
  display: flex; /* 使用Flexbox布局 */
  align-items: center; /* 垂直居中对齐 */
  justify-content: center;
}

.nextbutton{
  margin-left: 100px;
}

</style>
