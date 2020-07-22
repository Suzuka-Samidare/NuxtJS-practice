<template>
  <div style="margin: 20px;">
    <h1 class="page-headline">
      PROFILE
    </h1>
    <div style="margin: 20px; margin-bottom: 60px;">
      <div class="row">
        <h3>name</h3>
        <div style="margin-left: 20px;">
          さみだれ すずか
        </div>
      </div>
      <div class="row">
        <h3>favorite</h3>
        <div style="margin-left: 20px;">
          我那覇響（THE IDOLM@STER）
        </div>
      </div>
    </div>

    <nuxt-link
      to="/"
      tag="a"
      class="button--grey"
    >
      back
    </nuxt-link>
  </div>
</template>

<script>
export default {

}
</script>

<style>
.row {
  margin-bottom: 20px;
}

.button--grey {
  margin: 0;
}
</style>
