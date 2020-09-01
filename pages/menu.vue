<template>
  <div id="main-menu">
    <div class="container">
      <div class="content" style="width: 100%; font-size: 24px;">
        <div style="display: flex; justify-content: center;">
          <div class="button-group">
            <!-- <div class="button--cyan-dark">
              Profile
            </div>
            <button
              class="button--cyan-dark"
              style="background-color: #D6D6D6;"
            /> -->
            <nuxt-link to="profile" tag="div">
              <Button label="Profile" />
            </nuxt-link>
            <nuxt-link to="about" tag="div">
              <Button label="About" />
            </nuxt-link>
            <nuxt-link to="/" tag="div">
              <Button label="Exit" />
            </nuxt-link>
          </div>
        </div>
        <!-- <Button /> -->
        <!-- <div style="display: flex; justify-content: center;">
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
        </div> -->
      </div>
    </div>
  </div>
</template>

<script>
import Button from '@/components/Button'

export default {
  components: {
    Button
  },
  computed: {
    menuList () {
      return [
        { name: 'Profile', url: 'Profile' },
        { name: 'Blog', url: 'Blog' },
        { name: 'Link', url: 'Link' },
        { name: 'Navigation', url: 'Navigation' }
      ]
    }
  }
}
</script>

<style scope>
#main-menu {
  height: 100vh;
  width: 100vw;
}
.button-group {
  margin: 0 40px;
  max-width: 400px;
  /* min-width: 240px; */
  width: 100%;
}
</style>
