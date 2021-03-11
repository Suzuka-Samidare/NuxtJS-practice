<template>
  <div id="main-menu">
    <div class="common-area">
      <div class="buttons-block">
        <div class="button-group">
          <nuxt-link
            v-for="(item, index) in menuList"
            :key="index"
            :to="item.url"
            tag="div"
            style="margin: 12px 0;"
          >
            <Button :label="item.name" />
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
  },
  computed: {
    menuList () {
      return [
        { name: 'Profile', url: 'profile' },
        { name: 'About', url: 'about' },
        { name: 'Exit', url: '/' }
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
#main-menu .buttons-block {
  height: 100%;
  width: 100%;
  font-size: 24px;
  display: flex;
  justify-content: center;
  align-items: center;
}
#main-menu .button-group {
  margin: 0 40px;
  max-width: 400px;
  width: 100%;
}
</style>
