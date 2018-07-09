<template>
  <div class="Style">
    <!-- <pre>{{code}}</pre> -->
    <div class="pre" v-html="highlightedCode"></div>
    <div v-html="styleCode"></div>  
  </div>

</template>

<script>
import Prism from 'prismjs'
export default {
  name: 'Style',
  data () {
    return {
      code:'',
      findCode: `
         /*
         * Jabo
         */
         *{
            padding:0;
            margin:0;
         }

         body{
            background:#f99;
         }

         .token.comment{
           color:#ddd;
         }

         .token.selector{
          color:#f00;
         }

         .token.punctuation{
          color:#fff;
         }

         .token.property{
            color:green;
         }
      `,
    }
  },
  created(){
    let n = 0;
    setInterval(()=>{
        this.code = this.findCode.substring(0,n);
        n++;
    },100)
  },
  computed:{
    highlightedCode: function () {
      return Prism.highlight(this.code, Prism.languages.css)
    },
    styleCode(){
      return '<style>' + this.code + '</style>';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  
</style>
