<template>
  <div class="landing-page">
    <!-- <unitLeaderSection/> -->
    <h1 id="lp-logo">Projektor</h1>
    <h2 id="lp-subheader">Twój pomocnik w realizowaniu projektów starszoharcerskich!</h2>

    <div class="hero-circles">

      <div class="hero-div" id="hero1">
        <div class="hero-div-cover">
          <h3>Dla drużynowych /kadry</h3>
        </div>
        <img src="@/assets/heroImg1.jpg">
        <div class="description">
          <h3>Drużynowi/Kadra</h3>
          <span>Zobacz więcej</span>
        </div>
      </div>
      <div class="hero-div" id="hero2">
        <div class="hero-div-cover">
          <h3>Dla harcerzy starszych</h3>
        </div>
        <img src="@/assets/heroImg2.jpg">
        <div class="description">
          <h3>Harcerze starsi</h3>
          <span>Zobacz więcej</span>
        </div>
      </div>
      <div class="hero-div" id="hero3">
        <div class="hero-div-cover">
          <h3>Dla inspiracji</h3>
        </div>
        <img src="@/assets/heroImg3.jpg" id="libraryImg">
        <div class="description">
          <h3>Biblioteka projektów</h3>
          <span>Zobacz więcej</span>
        </div>
      </div>
    </div>
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
  $circle-color-1: #1941b1;
  $circle-color-1-darker: #0031b680;
  $circle-color-2: #473e10;
  $circle-color-2-darker: #473e1080;
  $circle-color-3: #8e4545;
  $circle-color-3-darker: #8e454580;


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

    & #lp-subheader::after {
      content: '';
      position: absolute;
      left: 0;
      top: 0;
      transform-origin: right;
      width: 100%;
      height: 100%;
      background-color: #F1F8FE; // background-color: black;
      filter: blur(5px);
      animation: subheader-slide-fade-in 2.5s cubic-bezier(0.63, 0.01, 0.43, 1.01) .5s both;
    }
    & #lp-subheader {
      position: relative;
      margin-top: 30px;
      animation: opacity-appear-effect 1.5s cubic-bezier(0, 0, 0.28, 1) 1.3s both;
    }
  }

  .hero-circles {
    margin: 100px 50px 0 50px;
    height: 200px;
    display: grid;
    justify-content: space-between;
    grid-template-columns: repeat(auto-fit, 200px);
    grid-column-gap: 40px;
    position: relative;

    &::after {
      content: '';
      position: absolute;
      left: -10%;
      top: -10%;
      width: 120%;
      height: 120%;
      transform-origin: bottom;
      background-color: #F1F8FE; // background-color: black;
      filter: blur(1px);
      animation: hero-circles-appear 1s ease-in 1.3s both;
    }

    & .hero-div {

      &:hover .hero-div-cover {
        height: 0;
      }

      .hero-div-cover {
        display: flex;
        cursor: pointer;
        width: 100%;
        height: 100%;
        justify-content: center;
        align-items: center;
        color: white;
        transition: height 0.2s ease-out;

        h3 {
          font-size: 1.7rem;
          line-break: auto;
        }
      }

      cursor: pointer;
      border: 1px solid #707070;
      border-radius: 50%;
      background-color: #fafafa;
      overflow: hidden;
      position: relative;

      &:hover .description {
        bottom: 0;
      }

      & .description {
        position: absolute;
        height: 40%;
        width: 100%;
        left: 0;
        bottom: -150%;
        background-color: #ffffffc4;
        transition: bottom .2s ease-out;

        & h3 {
          margin-top: 10px;
          font-size: .9rem;
          text-shadow: 0px 0px 13px rgba(255, 255, 255, 0.38);
        }
        & span {
          display: block;
          margin-top: 10px;
          font-size: .75rem;
          border: 1px dashed rgba(0, 49, 182, 0.5);
          font-weight: 900;
          padding: 1px 0px 2px;
          transition: background-color .2s ease-out;
          &:hover {
            background-color: white;
          }
        }
      } // &::after {
      //   content: "tekst";
      //   position: absolute;
      //   height: 40%;
      //   width: 100%;
      //   left: 0;
      //   bottom: 0;
      //   background-color: #fafafa;
      // }
      &#hero1 {
        -webkit-box-shadow: 0px 0px 20px 0px rgba(0, 49, 182, 1);
        -moz-box-shadow: 0px 0px 20px 0px rgba(0, 49, 182, 1);
        box-shadow: 0px 0px 20px 0px rgba(0, 49, 182, 1);
        animation: pulse1 2.6s ease-in-out both infinite;
        .hero-div-cover {
          background-color: $circle-color-1;
          // background-color: darken($color: $circle-color-1, $amount: 15%);
        }
      }

      &#hero2 {
        -webkit-box-shadow: 0px 0px 20px 0px rgba(71, 62, 16, 1);
        -moz-box-shadow: 0px 0px 20px 0px rgba(71, 62, 16, 1);
        box-shadow: 0px 0px 20px 0px rgba(71, 62, 16, 1);
        animation: pulse2 2.6s ease-in-out both infinite;
        .hero-div-cover {
          background-color: $circle-color-2;
          // background-color: darken($color: $circle-color-2, $amount: 15%);
        }
      }

      &#hero3 {
        -webkit-box-shadow: 0px 0px 20px 0px rgba(142, 69, 69, 1);
        -moz-box-shadow: 0px 0px 20px 0px rgba(142, 69, 69, 1);
        box-shadow: 0px 0px 20px 0px rgba(142, 69, 69, 1);
        animation: pulse3 2.6s ease-in-out both infinite;
        .hero-div-cover {
          background-color: $circle-color-3;
          // background-color: darken($color: $circle-color-3, $amount: 15%);
        }
      }

      & img {
        height: 100%;
        width: 100%;
        object-fit: contain;
        transform: scale(1.51) translateX(-19px);

        &#libraryImg {
          object-fit: cover;
          transform: none;
        }

      }
    }


  } // ============ Animations ================
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
    0% {
      opacity: 1;
      transform-origin: right;
    }
    10% {
      opacity: 1;
    }
    99% {
      transform: scaleX(0.00001);
      display: none;
      content: '';
    }
    100% {
      opacity: 0;
      transform: scaleX(0.00001);
      content: unset;

    }
  }

  @keyframes pulse1 {
    0% {
      box-shadow: 0px 0px 20px 0px #0031b6;
    }
    50% {
      box-shadow: 0px 0px 20px 0px #0031b680;
    }
    100% {
      box-shadow: 0px 0px 20px 0px #0031b6;
    }
  }

  @keyframes pulse2 {
    0% {
      box-shadow: 0px 0px 20px 0px #473e10;
    }
    50% {
      box-shadow: 0px 0px 20px 0px #473e1080;
    }
    100% {
      box-shadow: 0px 0px 20px 0px #473e10;
    }
  }

  @keyframes pulse3 {
    0% {
      box-shadow: 0px 0px 20px 0px #8e4545;
    }
    50% {
      box-shadow: 0px 0px 20px 0px #8e454580;
    }
    100% {
      box-shadow: 0px 0px 20px 0px #8e4545;
    }
  }


  @keyframes hero-circles-appear {
    0% {
      transform: scale(1, 1);
      filter: drop-shadow(1);
    }
    100% {
      transform: scale(1, 0);
    }
  }
</style>