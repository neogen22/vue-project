<template>
  <head>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;9..40,500&family=Outfit:wght@500;600&display=swap" rel="stylesheet">
    <title>My First Vue Project</title>
  </head>
  <body>
    <template v-if="showTheMenu">
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
      width: undefined,
      burgerShow: false,
      showTheMenu: undefined,
      idsArrayForBurgerMenu: [],      
    }
  },
  methods: {
    burgerShowMethod() {
      this.burgerShow = true
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
    show() {
      if (this.width <= 450) {
        this.burgerShow = true
      }
    }
  },
  created() {
    this.width = window.innerWidth
      window.addEventListener('resize', () => {
        this.width = window.innerWidth
      })
  },
  watch: {
    width(value) {
      if (value < 451) {
        this.showTheMenu = true
        this.idsArrayForBurgerMenuMethod()
      }
      if (value > 450) {
        this.showTheMenu = false
      }
    }
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
    @media screen and (min-width: 1190px) {
      .wrapper-app {
        display: flex; 
        flex-direction: row;
      }
    }    
    @media screen and (min-width: 950px) and (max-width: 1190px)  {
      .wrapper-app {
        display: flex; 
        flex-direction: row;
      }
    }
    @media screen and (min-width: 450px) and (max-width: 950px)  {
      .wrapper-app {
        display: flex; 
        flex-direction: row;
      }
    }
    @media screen and (max-width: 450px)  {
      .wrapper-app {
        display: flex; 
        flex-direction: column;        
      }
      .hamburger-icon {
        position: fixed;
        top: 10;
        margin-left: 320px;
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
</style>
