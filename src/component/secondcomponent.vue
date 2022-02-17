<template>
  <div id="secondcomponent">
    <h1>I am another page</h1>
    <a> written by {{ author }} </a>
    <el-card class="box-card">
      <div slot="header" class="clearfix">
        <h2 style="line-height: 36px; color: #20A0FF">豆瓣电影排行榜</h2>
      </div>
      <div v-for="article in articles" class="text item">
        {{article.title}}
      </div>
    </el-card>
    <p> 感谢 <a href="https://github.com/showonne">showonne</a>大神的技术指导</p>
  </div>
</template>
 
<script>
export default {
  data() {
    return {
      author: "Frank",
      articles: [],
    }
  },
  mounted: function() {
    this.$http.jsonp('https://api.douban.com/v2/movie/top250?count=10', {}, {
        headers: {
        },
        emulateJSON: true
    }).then(function(response) {
      // 这里是处理正确的回调
 
        this.articles = response.data.subjects
        // this.articles = response.data["subjects"] 也可以
 
    }, function(response) {
        // 这里是处理错误的回调
        this.articles = [
          {
            title: "肖申克的救赎",
          },
          {
            title: "这个杀手不太冷",
          },
          {
            title: "霸王别姬",
          }
        ];
        console.log(response)
    });
  }
}
</script>
 
<style>
</style>