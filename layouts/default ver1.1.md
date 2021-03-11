<template>
  <div id="common">
    <div v-show="$route.name !== 'index'" id="app-bar" :class="activeMenuClass">
      <div :class="`bottom-border`">
        <div class="page-info">
          *Mode : {{ toCamelCase('test') }}
        </div>
      </div>
    </div>
    <div v-show="$route.name !== 'index'" id="bottom-bar" :class="activeMenuClass">
      <div :class="`top-border`">
        <div class="operation-info">
          <!-- <div class="content">
            Tab Key : Next
          </div> -->
          <!-- <div class="content">
            Shift + Tab key : Prev
          </div> -->
          <!-- <div class="content">
            Space Key : O.K.
          </div> -->
          <!-- <div class="content">
            Move Cursol : Select
          </div> -->
          <div class="content">
            {{ pressKeyLabel }} : O.K.
          </div>
          <div class="content">
            Please
          </div>
        </div>
      </div>
    </div>
    <!-- <div
      v-show="isShowNav"
      id="menu-nav"
    >
      <div class="container">
        <div class="content" style="width: 100%; font-size: 24px;">
          <div style="display: flex; justify-content: center;">
            <div class="button--cyan-dark">
              Profile
            </div>
            <button
              class="button--cyan-dark"
              style="background-color: #D6D6D6;"
            />
          </div>
          <div style="display: flex; justify-content: center;">
            <div class="button--cyan-dark">
              Blog
            </div>
            <div
              class="button--cyan-dark"
              style="background-color: #D6D6D6;"
            />
          </div>
          <div style="display: flex; justify-content: center;">
            <div class="button--cyan-dark">
              Link
            </div>
            <div
              class="button--cyan-dark"
              style="background-color: #D6D6D6;"
            />
          </div>
          <div style="display: flex; justify-content: center;">
            <div class="button--cyan-dark">
              Navigation
            </div>
            <div
              class="button--cyan-dark"
              style="background-color: #D6D6D6;"
            />
          </div>
        </div>
      </div>
    </div> -->
    <Nuxt />
  </div>
</template>

<script>
// import Icon from '@/components/icon'

export default {
  components: {
    // Icon
  },
  data () {
    return {
      isShowNav: false
    }
  },
  computed: {
    activeMenuClass () {
      if (this.isShowNav) {
        return 'active-menu'
      } else {
        return ''
      }
    },
    pressKeyLabel () {
      /**
       * SSRの仕様によって、windowオブジェクトが存在しないので、
       * process.client変数を用いてアクセスする
       */
      if (process.client) {
        const regexp = /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i
        if (navigator.userAgent.match(regexp) !== null) {
          return 'Touch'
        } else {
          return 'Click'
        }
      } else {
        return 'Click'
      }
    }
  },
  methods: {
    openMenu () {
      this.isShowNav = !this.isShowNav
    },
    toCamelCase (str) {
      const firstAlphabet = str.substr(0, 1).toUpperCase()
      const otherAlphabet = str.substr(1)
      return firstAlphabet + otherAlphabet
    }
  }
}
</script>

<style scope>
/* ----------------------------------
  Default Property
 */
html {
  font-family:
    /* 'Impact', */
    'Helvetica Neue',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    Arial,
    sans-serif;
  font-size: 20px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

/* ----------------------------------
  Custom Property
 */
:root {
  --bar-height: 60px;
}
#common {
  background: lightgrey;
  /* background: #F1AE07; */
  /* background: #01adb9; */
  /* background: #FFFFFF; */
}

/* debug */
.button--cyan-dark {
  display: inline-block;
  /* border-radius: 4px; */
  border: 2px solid white;
  color: white;
  background-color: #525252;
  text-decoration: none;
  margin: 5px 0;
  padding: 10px 30px;
  border-radius: 1px;
  /* font-family: 'Orbitron'; */
}
.button--cyan-dark:focus {
  outline: none;
  color: #2541b2;
  background-color: #a3eefd;
}
.button--cyan-dark:hover {
  color: #2541b2;
  background-color: #a3eefd;
}
.button--cyan-dark:active {
  outline: none;
  color: #2541b2;
  background-color: #629eaa;
}
/* debug */

/* Desktop */
#app-bar {
  background-color: transparent;
  width: 100vw;
  height: var(--bar-height);
  padding: 0 10px;
  position: fixed;
  display: flex;
  justify-content: center;
  align-items: flex-end;
}
.bottom-border {
  width: 100%;
  border-bottom: 3px solid black;
}
.page-info {
  margin: 0 2% 1px;
  font-size: 20px;
}
#bottom-bar {
  background-color: transparent;
  width: 100vw;
  height: var(--bar-height);
  padding: 0 10px;
  position: fixed;
  bottom: 0;
  display: flex;
  justify-content: center;
  align-items: flex-start;
}
.top-border {
  width: 100%;
  border-top: 3px solid black;
}
.operation-info {
  display: flex;
  margin: 8px 1% 0;
  font-size: 20px;
}
.operation-info > .content {
  flex: 0 0 calc(100% - 110px);
  border-left: 3px solid black;
  text-align: center;
}
/* .operation-info > .content:nth-last-of-type(2) {
  flex: 0 0 30%;
  text-align: center;
} */
.operation-info > .content:last-child {
  flex: 0 0 110px;
  color: #F97A10;
  border-left: 3px solid #F97A10;
  border-right: 3px solid black;
}
.active-menu {
  z-index: 100;
}
.active-menu .bottom-border {
  border-bottom: 3px solid white;
}
.active-menu .page-info {
  color: white;
}
.active-menu .top-border {
  border-top: 3px solid white;
}
.active-menu .content {
  color: white;
  border-left: 3px solid white;
}
.active-menu .content:last-child {
  border-right: 3px solid white;
}
/* @media screen and (max-width: 450px) {
  #app-bar {
    display: none;
  }
} */
.bar-nav-button {
  width: 200px;
  /* height: 100%; */
  text-align: center;
  color: #2541b2;
  text-decoration: none;
  padding: 10px 30px;
  font-family: 'Orbitron';
}
.bar-nav-button:hover {
  border-bottom: 2px solid wheat;
}

/* Responsive */
#app-bar-responsive {
  background-color: transparent;
  width: 100vw;
  height: var(--bar-height);
  position: fixed;
  display: flex;
  align-items: center;
}
@media screen and (min-width: 451px) {
  #app-bar-responsive {
    display: none;
  }
}
.menu-button {
  display: flex;
  justify-content: center;
  align-items: center;
  width: var(--bar-height);
  height: 70%;
  color: white;
  font-size: 25px;
  font-family: 'Orbitron';
  text-align: center;
  background-color: rgba(0,0,0,0.4);
  border-radius: 0 24px 24px 0;
}
.menu-button:active {
  color: yellow;
}
.menu-button > .mark {
  margin-bottom: 2px;
}
.mark > .alphabet {
  display: flex;
  align-items: center;
  height: 20px;
}
.alphabet.bottom {
  justify-content: center;
}

#menu-nav {
  position: fixed;
  width: 100%;
  height: 100%;
  background-color: rgba(0,0,0,0.9);
  color: white;
}
/* .container {
  display: flex;
  align-items: center;
  height: 100%;
  width: 100%;
  padding: var(--bar-height) 0;
} */
.common-area {
  /* display: flex;
  align-items: center; */
  height: 100%;
  width: 100%;
  padding: var(--bar-height) 10px;
}
</style>
