<template>
  <div id="app">
    <Style />
    <Resume />
  </div>
</template>

<script>
import Test from './components/Test'
import Style from './components/Style'
import Resume from './components/Resume'

export default {
  name: 'App',
  components: {
    Test,
    Style,
    Resume
  }
}
</script>

<style>
  .pre{
     white-space:pre;
   }

   .Style,.Resume{
      width:50%;
      float:left;
    }

</style>
