<template>
  <div id="app">
    <component :is="layout">
      <router-view />
    </component>
  </div>
</template>

<script>
import EmptyLayout from  '@/layouts/EmptyLayout'
import MainLayout from  '@/layouts/MaindLayout'
export default {
  computed: {
    layout() {
      // console.log(this.$route.meta);
      // console.log(this.$route.meta.myterm);
      // console.log("!!!");
      // return 'empty-layout'
      // return 'main-layout' 
      return (this.$route.meta.layout || 'empty') + '-layout'
    },
  },
  components: {
    EmptyLayout, MainLayout
  }
};
</script>

<style lang="scss">
@import "~materialize-css/dist/css/materialize.min.css";
@import "assets/index.css";
</style>
