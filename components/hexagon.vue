<template>
  <div id="hexagon" :style="hexagonColor" />
</template>

<script>
export default {
  props: {
    figureColor: {
      type: String,
      default: '#9ce7eb',
      required: false
    }
  },
  computed: {
    hexagonColor () {
      return `background-color: ${this.figureColor};
              border-color: ${this.figureColor};`
    }
  }
}
</script>

<style>
/* #hexagon {
  position: relative;
  width: 100px;
  height: 57.74px;
  background-color: inherit;
  margin: 28.87px 0;
}

#hexagon:before,
#hexagon:after {
  content: "";
  position: absolute;
  width: 0;
  border-left: 50px solid transparent;
  border-right: 50px solid transparent;
}

#hexagon:before {
  bottom: 100%;
  border-bottom: 28.87px solid;
  border-bottom-color: inherit;
}

#hexagon:after {
  top: 100%;
  width: 0;
  border-top: 28.87px solid;
  border-top-color: inherit;
} */

#hexagon {
  position: relative;
  width: 80px;
  height: 46.19px;
  background-color: inherit;
  margin: 23.09px 0;
}

#hexagon:before,
#hexagon:after {
  content: "";
  position: absolute;
  width: 0;
  border-left: 40px solid transparent;
  border-right: 40px solid transparent;
}

#hexagon:before {
  bottom: 100%;
  border-bottom: 23.09px solid;
  border-bottom-color: inherit;
}

#hexagon:after {
  top: 100%;
  width: 0;
  border-top: 23.09px solid;
  border-top-color: inherit;
}
</style>
