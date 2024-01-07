<template>
  <head>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;9..40,500&family=Outfit:wght@500;600&display=swap" rel="stylesheet">
    <title>My First Vue Project</title>
  </head>
  <body>    
    <template v-if="portrait">
      <div class="hamburger-icon" @click="burgerShowMethod()">
        <img src="/public/hamburgerMenu.svg" height="35vh">
      </div>
      <div @click="burgerCloseMethod()">
        <div class="burger-menu" v-if="burgerShow">    
          <ul class="burger-menu-ul" >
            <li v-for="item in idsArrayForBurgerMenu" :key="item.id"><a :href="item.id">{{item.name}}</a></li>
          </ul>
        </div>
        <div class="wrapper-app">
          <AsideComponent/>
          <MainPartFullComponent/>
        </div>
      </div>
    </template> 
    <div class="wrapper-app" v-else>
        <AsideComponent/>
        <MainPartFullComponent/>
    </div>    
  </body>
</template>

<script>
import AsideComponent from './components/AsidePartComponents/AsidePartFullComponent.vue';
import MainPartFullComponent from './components/MainPartComponents/MainPartFullComponent.vue';

export default {
  components: {    
    AsideComponent,
    MainPartFullComponent,   
  },
  data() {
    return {
      burgerShow: false,
      idsArrayForBurgerMenu: [],
      deviceWidth: 0,
      deviceHeight: 0,
      portrait: undefined,
    }
  },
  methods: {
    burgerShowMethod() {
      this.burgerShow = !this.burgerShow
    },
    burgerCloseMethod() {
      if (this.burgerShow) {
        this.burgerShow = false
      }
    },
    idsArrayForBurgerMenuMethod() {
      if (this.idsArrayForBurgerMenu.length === 0) {
        for (let i of document.querySelectorAll('.header-of-main-part')) {
          if (i.id !== '') {
            this.idsArrayForBurgerMenu.push({
              id: `#${i.id}`,
              name: `${i.id}`
            })
          }
        }
      }
      return this.idsArrayForBurgerMenu
    },
    changeScreenMethod() {
      return this.deviceHeight > this.deviceWidth
    }
  },  
  mounted() {
    this.deviceWidth = window.innerWidth
    this.deviceHeight = window.innerHeight
    window.addEventListener('resize', () => {
      this.deviceWidth = window.innerWidth
      this.deviceHeight = window.innerHeight
    })
  },
  watch: {
    deviceWidth() {
      if (this.deviceHeight > this.deviceWidth) {
        this.portrait = true
        this.idsArrayForBurgerMenuMethod()
      } else {
        this.portrait = false
      }
    }
  }  
}
</script>

<style scoped>
    @media (orientation: portrait) {
      .hamburger-icon {
        position: fixed;
        top: 10;
        margin-left: 75vw;
        z-index: 2;
      }
      .hamburger-icon .active {
        position: fixed;
        top: 10;
        margin-left: 75vw;
        z-index: 2;
        transform: rotate(90deg);
        transition: all 250ms;
      }
      .burger-menu {
        position: fixed;
        top: 20;      
        z-index: 1;
        margin-left: 23vw;
        margin-top: 4vh;
      }
      .burger-menu li {
        list-style-type: none;
        color: white;
        padding: 0;
        -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
      }
      .burger-menu-ul {
        margin-left: 40vw;
        background-color: rgb(152, 165, 223);
        padding: 1vw;
        padding-left: 2vw;     
        margin: 0;
        border-radius: 5%;        
      }
      a {
        color: white;
        font-size: 3vh;
      }
      a:hover {
        color: black;
        transition: transform 15s;
      }
    }
    body {
        padding: 0;
        margin: 0;
    }
    *, *::before, *::after {
        font-weight: inherit;
    }
    @media (orientation: portrait) {
        .wrapper-app {
          display: flex; 
          flex-direction: column;
      }
    }
    @media (orientation: landscape) {
      .wrapper-app {
        display: flex; 
        flex-direction: row;
      }
    }
</style>
