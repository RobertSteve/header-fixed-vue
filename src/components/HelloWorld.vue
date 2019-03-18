<template>
  <div :id="'container'+idHeader">
    <div class="header">
      {{title}}
    </div>
    <div class="section" style="height:1000px; width:100%; background-color: blue;">
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      active: 1
    }
  },
  props: {
   idHeader: {
     default: null
   },
   title:{
     default: null
   }
  },
  computed: {
  },
  mounted() {
    window.addEventListener(
      "scroll",
      function(){
        var a = document.getElementById("container"+this.idHeader).getBoundingClientRect();
        if(a.top<=0 && a.height>=a.top*-1){
          document.getElementById("headerFixed").style.display = "block";
          this.$emit('title', this.title)
        }
      }.bind(this)
    )
  },
}
</script>
<style>
  .header{
    width: 100%;
    height: 80px;
    background-color: red;
  }
  .headerFixed{
    width: 100%;
    height: 80px;
    background-color: saddlebrown;
    position: fixed;
    top: 0;
    display: none;
  }
</style>
