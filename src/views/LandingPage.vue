<template>
  <div class="landing-page">
    <!-- <unitLeaderSection/> -->
    <h1 id="lp-logo">Projektor</h1>
    <h2 id="lp-subheader">Twój pomocnik w realizowaniu projektów starszoharcerskich!</h2>
  </div>
</template>

<script>
  // @ is an alias to /src
  import unitLeaderSection from '@/components/unitLeaderSection.vue'

  export default {
    name: 'home',
    components: {
      unitLeaderSection
    }
  }
</script>

<style lang="scss" scoped>
  .landing-page {
    padding-top: 40px;

    & #lp-logo {
      display: inline-block;
      font-size: 3em;
      position: relative;
      animation: opacity-appear-effect 1s ease-in-out both 0.2s;
      &::after {
        content: '';
        height: 1px;
        border-radius: 20px;
        width: 90%;
        right: -20px;
        position: absolute;
        background-color: black;
        bottom: -12px;
        box-shadow: 2px 2px 6px 0px rgba(78, 25, 25, 1);
        transition: opacity 1s ease-in-out;
        
        animation: underline-appear-anim 2.3s cubic-bezier(0, 0, 0.28, 1) 0.5s both,
        underline-move-around 2s cubic-bezier(0.72, 0.01, 0.37, 1.01) 4s 8 alternate both,
        underline-finale 2s cubic-bezier(0.65, 0.01, 0.26, 0.99) 18s normal forwards;
      }
    }

    & #lp-subheader::after{
      content: '';
      position: absolute;
      left: 0;
      top: 0;
      transform-origin: right;
      width: 100%;
      height: 100%;
      background-color: #F1F8FE;
      // background-color: black;
      filter: blur(5px);
      animation: subheader-slide-fade-in 2.5s cubic-bezier(0.63, 0.01, 0.43, 1.01) .5s both;
    }
    & #lp-subheader{
      position: relative;
      margin-top: 30px;
      animation: opacity-appear-effect 1.5s cubic-bezier(0, 0, 0.28, 1) 1.3s both;
    }
  } 
  
  
  
  
  // ============ Animations ================
  @keyframes opacity-appear-effect {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }

  @keyframes underline-appear-anim {
    0% {
      left: 0;
      width: 10%;
      opacity: 0;
    }
    70% {
      opacity: 1;
    }
    85% {
      left: 40px;
      width: 88%;
    }

    100% {
      left: 40px;
      width: 88%;
    }

  }

  @keyframes underline-move-around {
    0% {
      left: 40px;
      transform: scaleX(.7);
    }

    100% {
      left: 0px;
      transform: scaleX(.7);
    }
  }

  @keyframes underline-finale {
    0% {
      transform: scaleX(.7);
      opacity: 1;
    }
    100% {
      transform: scaleX(1.01);
      opacity: 0.4;
    }
  }

  @keyframes subheader-slide-fade-in {
    0%{
      opacity: 1;
      transform-origin: right;
    }
    10%{
      opacity: 1;
    }
    99%{
      transform: scaleX(0.00001);
      display: none;
      content: '';
    }
    100%{
      opacity: 0;
      transform: scaleX(0.00001);
      content: unset;

    }
  }

</style>