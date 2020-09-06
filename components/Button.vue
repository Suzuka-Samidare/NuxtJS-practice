<template>
  <div class="button-root button-outline">
    <div class="button-label">
      {{ label }}
    </div>
    <div class="button-toggle">
      <div class="toggle" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: ''
    }
  }
}
</script>

<style scope>
.button-root {
  --button-toggle-width: 50px;
}

.button-outline {
  border: 2px solid #FFFFFF;
  border-radius: 2px;
  display: flex;
  /* margin: 12px 0; */
}

.button-label {
  color: #FFFFFF;
  background-color: #525252;
  border-right: 2px solid #FFFFFF;
  padding: 6px 16px;
  text-align: left;
  text-decoration: none;
  width: calc(100% - var(--button-toggle-width));
}
.button-toggle {
  align-items: center;
  background-color: #D6D6D6;
  display: flex;
  justify-content: center;
  width: var(--button-toggle-width);
}
.button-toggle > .toggle {
  background-color: #D6D6D6;
  border-bottom: 2px solid darkslategray;
  border-left: 2px solid #FFFFFF;
  border-right: 2px solid darkslategray;
  border-top: 2px solid #FFFFFF;
  height: 18px;
  width: 18px;
}
</style>
