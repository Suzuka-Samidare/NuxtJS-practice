<template>
  <div>
    <h1 id="header">
      Suzuka-Samidare Practice NuxtJS
    </h1>
    <Nuxt />
  </div>
</template>

<style>
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

#header {
  background-color: rgb(0, 194, 194);
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
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

.button--cyan {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid rgb(1, 148, 148);
  color: rgb(1, 148, 148);
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--cyan:hover {
  color: #fff;
  background-color: rgb(1, 148, 148);
}

.page-headline {
  margin-bottom: 24px;
}
</style>
