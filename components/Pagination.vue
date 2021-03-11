<template>
  <div class="pagination-root pagination-outline">
    <div class="pagination-label">
      <span>Section {{ bindValue }}/{{ length }}</span>
      <span class="pagination-label-name">| AAAAA</span>
    </div>
    <div
      v-for="n of length"
      :key="n"
      class="pagination-toggle"
      @click="pageChange(n)"
    >
      <div class="toggle" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    bindValue: {
      type: Number,
      default: 1
    },
    length: {
      type: Number,
      default: 1
    }
  },
  methods: {
    pageChange (page) {
      this.$emit('update:bindValue', page)
    }
  }
}
</script>

<style scope>
.pagination-root {
  --pagination-toggle-width: 40px;
}

.pagination-outline {
  border: 2px solid #FFFFFF;
  border-radius: 2px;
  display: flex;
}

.pagination-label {
  color: #FFFFFF;
  background-color: #525252;
  border-right: 2px solid #FFFFFF;
  padding: 6px 16px;
  text-align: left;
  text-decoration: none;
}

.pagination-label-name {
  display: none;
}

.pagination-toggle {
  align-items: center;
  background-color: #D6D6D6;
  display: flex;
  justify-content: center;
  width: var(--pagination-toggle-width);
}
.pagination-toggle > .toggle {
  background-color: #D6D6D6;
  border-bottom: 2px solid darkslategray;
  border-left: 2px solid #FFFFFF;
  border-right: 2px solid darkslategray;
  border-top: 2px solid #FFFFFF;
  height: 18px;
  width: 18px;
}
</style>
