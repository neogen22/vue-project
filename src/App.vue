<template>
  <head>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;9..40,500&family=Outfit:wght@500;600&display=swap" rel="stylesheet">
    <title>My First Vue Project</title>
  </head>
  <div class="wrapper-app">
    <AsideComponent/>
    <MainPartFullComponent/>
  </div>
</template>

<script>
import AsideComponent from './components/AsidePartComponents/AsidePartFullComponent.vue';
import MainPartFullComponent from './components/MainPartComponents/MainPartFullComponent.vue';

export default {
  components: {    
    AsideComponent,
    MainPartFullComponent
  }
}
</script>

<style scoped>
    body {
        padding: 0;
        margin: 0;
    }
    *, *::before, *::after {
        font-weight: inherit;
    }
    .wrapper-app {
        display: flex; 
        flex-direction: row;
    }
    @media (orientation: portrait) {
      .wrapper-app {
        display: flex; 
        flex-direction: column;
      }
    }
</style>
