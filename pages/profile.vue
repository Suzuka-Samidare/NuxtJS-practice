<template>
  <div id="profile" class="profile-root">
    <div class="button-group">
      <nuxt-link to="menu" tag="div">
        <Button label="Back" />
      </nuxt-link>
    </div>
    <div class="content-container">
      <div class="image-window">
        <div class="outline">
          <div class="icon">
            <img src="~/static/Suzuka-Samidare_icon.png" alt="">
          </div>
        </div>
      </div>
      <p>Name : Suzuka-Samidare</p>
      <div class="skill-content">
        <div>Skill : </div>
        <div>
          <ul>
            <li>JavaScript</li>
            <li>Vue.js</li>
            <li>Python</li>
            <li>bottle</li>
            <li>django</li>
            <li>Angular</li>
            <li>nuxt.js</li>
          </ul>
        </div>
      </div>
      <p>Side Job : 765Production Producer</p>
      <p>Favorite : Cat, Anime, Game(Racing), Car</p>
    </div>
    <MessageWindow />
  </div>
</template>

<script>
import Button from '@/components/Button'
import MessageWindow from '@/components/messageWindow'
export default {
  components: {
    Button,
    MessageWindow
  }
}
</script>

<style scope>
#profile {
  width: 100vw;
  height: 100vh;
  padding: var(--bar-height) 10px; /* default.vue :root */
  /* background: linear-gradient(#43D4D4, #1768ac); */
}

.button-group {
  margin: 0 40px;
  max-width: 400px;
  /* min-width: 200px; */
  width: 100%;
}

.content-container {
  border-left: 5px solid #4E504C;
  margin: 8px;
  padding: 8px;
}

.image-window > .outline {
  --icon-outline-length: 100px;
  --icon-outline-border-width: 4px;
  --icon-margin: 5px;
  --icon-length: calc(var(--icon-outline-length)
     - (var(--icon-outline-border-width) * 2)
     - (var(--icon-margin) * 2)
  );
  border: var(--icon-outline-border-width) solid #000000;
  height: var(--icon-outline-length);
  width: var(--icon-outline-length);
}

.image-window .icon {
  margin: var(--icon-margin);
  /* width: var(--icon-length);
  height: var(--icon-length); */
  /* min-width: 100px;
  min-height: 100px; */
  background-color: #FFFFFF;
  display: flex;
  justify-content: center;
  align-items: center;
}

.icon img {
  width: var(--icon-length);
  height: var(--icon-length);
}

.skill-content {
  display: flex;
}
.skill-content ul {
  padding: 0 5px;
}
.skill-content li {
  list-style-type: none;
}

.row {
  margin-bottom: 30px;
}

.row h3 {
  font-family: 'Orbitron';
  margin-bottom: 5px;
}

.button--grey {
  margin: 0;
}
</style>
