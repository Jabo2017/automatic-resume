<template>
  <div class="Resume" v-html="markedCode"></div>

</template>

<script>
import Marked from 'marked'
export default {
  name: 'Marked',
  data () {
    return {
      markedCode:'',
      fullMarkdown: `Jabo
----
前端工程师

技能
----

* 前端开发
* vue 开发
* Node.js 开发
* 前端授课

工作经历
----

1. 福建威宏贸易
2. 厦门金猪网络
3. 网龙公司
4. 亿策中启集团

链接
----

* [GitHub](https://github.com/jabo2017)

`
    }
  },
  created(){
    this.whiteMarked();
  },
  computed:{
    
  },
  methods:{
    whiteMarked(){
      let n = 0;
      setInterval(()=>{
          this.markedCode = this.fullMarkdown.substring(0,n);
          if(this.markedCode.length == this.fullMarkdown.length ){
             this.markedCode = Marked(this.markedCode);
          }
          n++;
      },250)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .Resume{
    white-space: pre;
  }
</style>
