<template>
  
    <AppHeader />
      <AppMain />
    <AppFooter />
 
  
</template>

<script>
import AppFooter from './components/Footer/AppFooter.vue';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/Main/AppMain.vue';
export default {
  components: {
    AppHeader,
    AppMain,
    AppFooter
  }
}
</script> 

<style lang="scss" scoped></style>