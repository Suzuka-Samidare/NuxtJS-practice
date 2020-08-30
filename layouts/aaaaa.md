```
<template>
  <div>
    <!-- <div id="app-bar">
      <nuxt-link
        to="profile"
        tag="a"
        class="bar-nav-button"
      >
        Profile
      </nuxt-link>
      <nuxt-link
        to="profile"
        tag="a"
        class="bar-nav-button"
      >
        Profile
      </nuxt-link>
      <nuxt-link
        to="profile"
        tag="a"
        class="bar-nav-button"
      >
        Profile
      </nuxt-link>
    </div>
    <div id="app-bar-responsive">
      <div class="menu-button" @click="openMenu()">
        <div class="mark">
          <div class="alphabet top">
            me
          </div>
          <div class="alphabet bottom">
            nu
          </div>
        </div>
      </div>
    </div>
    <div
      v-show="isShowNav"
      id="menu-nav"
    >
      NAVGATION
    </div>
    <Nuxt style="height: 100vh;" /> -->
  </div>
</template>

<script>
// import Icon from '@/components/icon'

export default {
//   components: {
//     // Icon
//   },
//   data () {
//     return {
//       isShowNav: false
//     }
//   },
//   methods: {
//     openMenu () {
//       this.isShowNav = true
//     }
//   }
}
</script>

<style>
/* ----------------------------------
  Default Property
 */
html {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
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
.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}
.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}
.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}
.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}

/* ----------------------------------
  Custom Property
 */
:root {
  --app-bar-height: 80px;
}
.button--cyan {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid rgb(1, 148, 148);
  color: rgb(1, 148, 148);
  text-decoration: none;
  padding: 10px 30px;
}
.button--cyan:hover {
  color: #fff;
  background-color: rgb(1, 148, 148);
}
.button--cyan-dark {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #a3eefd;
  color: #a3eefd;
  text-decoration: none;
  padding: 10px 30px;
  font-family: 'Orbitron';
}
.button--cyan-dark:hover {
  color: #2541b2;
  background-color: #a3eefd;
}

/* Desktop */
#app-bar {
  background-color: transparent;
  width: 100vw;
  height: var(--app-bar-height);
  position: fixed;
  display: flex;
  justify-content: center;
  align-items: center;
}
@media screen and (max-width: 450px) {
  #app-bar {
    display: none;
  }
}
.bar-nav-button {
  width: 200px;
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
  height: var(--app-bar-height);
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
  width: var(--app-bar-height);
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
  background-color: rgba(0,0,0,0.95);
  color: white;
}
</style>
```
