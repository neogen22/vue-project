<script>
import AsideComponent from './components/AsidePartComponents/AsidePartFullComponent.vue';
import MainCard from './components/MainPartComponents/MainPartFullComponent.vue';

export default {
  components: {    
    AsideComponent,
    MainCard
  }
}
</script>

<template>
  <div style="display: flex; flex-direction: row; column-gap: 16px">
    <AsideComponent/>
    <MainCard/>
  </div>
</template>

<style scoped>
body {
  padding: 0;
  margin: 0;
}
</style>

