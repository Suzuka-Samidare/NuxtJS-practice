<template>
  <div id="top-page" @click="$router.push('Menu')">
    <!-- <div class="home-container flex-center"> -->
    <div class="container">
      <div class="content">
        <div class="logo">
          <h1 class="title">
            <span class="span1">Suzuka-Samidare</span>
            <br class="br">
            <span class="span2">Expression Site</span>
          </h1>
        </div>
        <div class="press-info">
          <h2>*{{ pressInfoLabel }}</h2>
        </div>
      </div>
    </div>
    <!-- </div> -->
    <!-- <div style="position: absolute; width: 100px; height: 115.3px;">
      <Hexagon
        v-for="(params, index) in hexagons"
        :key="index"
        :figure-color="params.color"
        :style="hexagonStyle(params)"
      />
    </div> -->
  </div>
</template>

<script>
// import Hexagon from '../components/hexagon'

export default {
  components: {
    // Hexagon
  },
  computed: {
    hexagons () {
      return [
        { color: '#06bee1', top: '', bottom: '', left: '', right: '' },
        { color: '#1768ac', top: '100px', bottom: '', left: '', right: '60px' },
        { color: '#2541b2', top: '100px', bottom: '', left: '60px', right: '' },
        { color: '#3563C8', top: '100px', bottom: '', left: '180px', right: '' }, // 03256c
        { color: '#06bee1', top: '', bottom: '', left: '240px', right: '' },
        { color: '#1768ac', top: '', bottom: '100px', left: '', right: '60px' },
        { color: '#3563C8', top: '', bottom: '100px', left: '', right: '180px' },
        { color: '#06bee1', top: '', bottom: '', left: '', right: '240px' }
      ]
    },
    pressInfoLabel () {
      /**
       * SSRの仕様によって、windowオブジェクトが存在しないので、
       * process.client変数を用いてアクセスする
       */
      if (process.client) {
        const regexp = /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i
        if (navigator.userAgent.match(regexp) !== null) {
          return 'TOUCH SCREEN'
        } else {
          // return 'PRESS SPACE KEY or CLICK SCREEN'
          return 'CLICK SCREEN'
        }
      } else {
        return 'CLICK SCREEN'
      }
    }
  },
  methods: {
    hexagonStyle (params) {
      return `position: absolute;
              top: ${params.top};
              bottom: ${params.bottom};
              left: ${params.left};
              right: ${params.right};
              opacity: 0.6;`
    }
  }
}
</script>

<style scoped>
#top-page {
  height: 100vh;
  width: 100vw;
  /* background: #F1AE07; */
  /* background: #01adb9; */
  /* background: #FFFFFF; */
}

/* .container {
  display: flex;
  align-items: center;
  height: 100%;
  width: 100%;
  padding: var(--bar-height) 0;
} */

.home-container {
  width: 100vw;
  height: 100vh;
  /* background: linear-gradient(#43D4D4, #1768ac); */
}

.logo {
  display: flex;
  justify-content: space-around;
  align-items: center;
  width: 100vw;
  /* height: 450px; */
  margin-bottom: 60px;
  padding: 0 10px;
}

h1.title {
  color: black;
  text-align: center;
  font-family: 'Orbitron';
  font-weight: bold;
  font-size: 60px;
  /* z-index: 50; */
}

.press-info {
  display: flex;
  justify-content: center;
}

@media screen and (max-width: 339px) {
  h1.title {
    font-size: 38px;
  }
  .press-info {
    font-size: 14px;
  }
}

@media screen and (min-width: 340px) and (max-width: 479px) {
  h1.title {
    font-size: 50px;
  }
  .press-info {
    font-size: 16px;
  }
}

@media screen and (min-width: 1159px) {
  h1.title > .br {
    display: none;
  }
}
</style>
