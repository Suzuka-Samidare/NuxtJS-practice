<template>
  <div id="about">
    <div class="common-area">
      <div class="source-block">
        <div class="source-logo-container">
          <Logo />
          <h1 class="title">
            nuxtjs-tutorial
          </h1>
          <!-- <div class="links">
            <nuxt-link to="menu" tag="div">
              <Button label="Back" />
            </nuxt-link>
          </div> -->
        </div>
      </div>
      <div class="buttons-block">
        <div class="button-group">
          <nuxt-link
            to="menu"
            tag="div"
          >
            <Button label="Back" />
          </nuxt-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Button from '@/components/Button'
export default {
  components: {
    Button
  }
}
</script>

<style>
#about {
  height: 100vh;
  width: 100vw;
}
#about .source-block {
  height: 80%;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
#about .source-logo-container {
  text-align: center;
}

.source-logo-container > h1.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

@media screen and (max-width: 389px) {
  .source-logo-container > h1.title {
    font-size: 40px;
  }
}

@media screen and (min-width: 390px) and (max-width: 659px) {
  .source-logo-container > h1.title {
    font-size: 60px;
  }
}

/* @media screen and (min-width: 1159px) {
  h1.title > .br {
    display: none;
  }
} */

/* .subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
} */

#about .buttons-block {
  height: 20%;
  width: 100%;
  font-size: 24px;
  display: flex;
  justify-content: center;
  align-items: center;
}
#about .button-group {
  margin: 0 40px;
  max-width: 400px;
  width: 100%;
}

.links {
  padding-top: 15px;
}
</style>
