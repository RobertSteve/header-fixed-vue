<template>
  <div id="app">
    <div class="logo"></div>
    <div class="headerFixed" id="headerFixed">
      {{titleFixed}}
    </div>
    <HelloWorld id-header="1" :title="title1" v-on:title="title"/>
    <HelloWorld id-header="2" :title="title2" v-on:title="title"/>
    <HelloWorld id-header="3" :title="title3" v-on:title="title"/>
    <HelloWorld id-header="4" :title="title4" v-on:title="title"/>
    <HelloWorld id-header="5" :title="title5" v-on:title="title"/>
    <HelloWorld id-header="6" :title="title6" v-on:title="title"/>

    
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  data() {
    return {
      titleFixed: "",
      title1: "titulo 1",
      title2: "titulo 2",
      title3: "titulo 3",
      title4: "titulo 4",
      title5: "titulo 5",
      title6: "titulo 6",

    }
  },
  components: {
    HelloWorld
  },
  methods: {
    title: function (a){
      this.titleFixed = a;
    }
  },
  mounted(){
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
}
.logo{
  height: 60px;
  width: 100%;
  background-color: aqua;
}
</style>
