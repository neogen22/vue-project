<script>
import FirstPage from './components/FirstPageComponents/FirstPage.vue';
import SecondPage from './components/SecondPageComponents/SecondPage.vue';

export default {
  components: {    
    SecondPage,
    FirstPage
  }
}
</script>

<template>
  <div style="display: flex; flex-direction: row; column-gap: 16px">
    <FirstPage/>
    <SecondPage/>
  </div>
</template>

<style scoped>
body {
  padding: 0;
  margin: 0;
}
</style>

