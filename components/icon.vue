<template>
  <i :class="iconClass" />
</template>

<script>
export default {
  props: {
    iconClass: {
      type: String,
      required: true
    }
  }
}
</script>

<style scope>
i {
  font-size: 40px;
}
</style>
