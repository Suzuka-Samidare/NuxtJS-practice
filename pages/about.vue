<template>
  <div id="about" class="container">
    <div>
      <Logo />
      <h1 class="title">
        nuxtjs-tutorial
      </h1>
      <div style="display: flex; justify-content: center; margin: 15px;">
        <div class="button-group">
          <div style="margin: 12px 0;">
            <a
              href="https://github.com/Suzuka-Samidare/NuxtJS-practice"
              target="_blank"
              rel="noopener noreferrer"
              style="text-decoration: none;"
            >
              <Button label="Jump to github/NuxtJS-practice" />
            </a>
          </div>
          <div style="margin: 12px 0;">
            <a
              href="https://github.com/nuxt/nuxt.js"
              target="_blank"
              rel="noopener noreferrer"
              style="margin: 12px 0; text-decoration: none;"
            >
              <Button label="Jump to github/nuxt.js" />
            </a>
          </div>
          <nuxt-link to="menu" tag="div" style="margin: 12px 0;">
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
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
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

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

#about .button-group {
  margin: 0 40px;
  max-width: 400px;
  /* min-width: 240px; */
  width: 100%;
}
</style>
