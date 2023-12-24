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
  <head>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;9..40,500&family=Outfit:wght@500;600&display=swap" rel="stylesheet">
    <title>My First Vue Project</title>
  </head>
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
*, *::before, *::after {
  font-weight: inherit;
}

</style>

