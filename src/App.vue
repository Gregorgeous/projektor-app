<template>
  <div id="app">
    <nav id="navigation" class="navbar" role="navigation" aria-label="main navigation">
      <div class="FTLLogo">
      <scoutLogoTop id="FTLLogo--top" ></scoutLogoTop>
      <span id="FTLLogo--middle">Wejdź do systemu</span>
      <scoutLogoBottom id="FTLLogo--bottom"></scoutLogoBottom>
      </div>
      <!-- <router-link to="/">Home</router-link> -->
    </nav>
    <main>
      <router-view/>
    </main>
  </div>
</template>

<script>
// @ is an alias to /src
import scoutLogoTop from '@/components/Scout-website-logo/scoutLogoTopSvg.vue'
import scoutLogoBottom from '@/components/Scout-website-logo/scoutLogoBottomSvg.vue'


export default {
  name: 'home',
  components: {
    scoutLogoTop,
    scoutLogoBottom
  }
}
</script>

<style lang="scss">
  html {
    height: 100vh;
  }
  body{
    margin: 0 0 8px;
  }

  main{
    background-color: #F1F8FE;
    height: 90vh; //TODO: change this later
  }

  .FTLLogo{
    fill: #483077;
    cursor: pointer;
    align-self: stretch;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    &:hover{
      -webkit-animation: rotate-90 0.4s cubic-bezier(0.250, 0.460, 0.450, 0.940) both;
	        animation: rotate-90 0.4s cubic-bezier(0.250, 0.460, 0.450, 0.940) both ;
          & #FTLLogo--top{
            animation: move-top 0.4s cubic-bezier(0.250, 0.460, 0.450, 0.940) both  0.25s;
          }
          & #FTLLogo--bottom{
            animation: move-bottom 0.4s cubic-bezier(0.250, 0.460, 0.450, 0.940) both  0.25s;
          }
          & #FTLLogo--middle{
            animation: rotate-and-scale 0.4s cubic-bezier(0.250, 0.460, 0.450, 0.940) both  0.1s;
          }
    } 
  }

@keyframes rotate-90 {
  0% {
    -webkit-transform: rotate(0);
            transform: rotate(0);
  }
  100%{
    -webkit-transform: rotate(90deg);
            transform: rotate(90deg) translateY(-20px);
  }
}

@keyframes rotate-and-scale {
  0%{
    transform: rotate(0);
    font-size: 5px;
  }
  70%{
    font-size: 5px;
    transform: rotate(-90deg);
  }
  
  100%{
    transform: rotate(-90deg);
    font-size: 15px;
  }
}

@keyframes move-top{
  from{
    transform: translateY(0)
  }
  to{
    transform: translateY(-60px);
  }
}

@keyframes move-bottom{
  from{
    transform: translateY(0)
  }
  to{
    transform: translateY(60px);
  }
}


  #FTLLogo--top{
    height: 25px;
  }

  #FTLLogo--middle{
    font-size: 7px;
    pointer-events: none
  }

  #FTLLogo--bottom{
    height: 13px;
  }
  #app {
    position: relative;
    margin: 0;
    padding: 0;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }

  #navigation {
    position: relative;
    z-index: 99;
    height: 10vh;
    display: flex;
    justify-content: center;
    align-content: center;
    align-items: center;
    -webkit-box-shadow: 0px 3px 15px 0px rgba(0, 0, 0, 0.16);
    -moz-box-shadow: 0px 3px 15px 0px rgba(0, 0, 0, 0.16);
    box-shadow: 0px 3px 15px 0px rgba(0, 0, 0, 0.16);
    a {
      font-weight: bold;
      color: #2c3e50;
      &.router-link-exact-active {
        color: #42b983;
      }
    }
  }
</style>