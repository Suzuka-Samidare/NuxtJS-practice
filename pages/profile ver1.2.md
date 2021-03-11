<template>
  <div id="profile" class="profile-root">
    <div class="common-area">
      <div class="image-block">
        <div class="content_image-window">
          <div class="outline">
            <div class="icon">
              <img src="~/static/Suzuka-Samidare_icon.png" alt="">
            </div>
          </div>
        </div>
      </div>
      <div class="message-window-block">
        <MessageWindow :messages="messages" />
      </div>
    </div>
  </div>
  <!-- <div id="profile" class="profile-root">
    <div class="wrap-pagination">
      <Pagination
        :bind-value.sync="section"
        :length="3"
      />
    </div>
    <div class="content">
      <div class="content_image-window">
        <div class="outline">
          <div class="icon">
            <img src="~/static/Suzuka-Samidare_icon.png" alt="">
          </div>
        </div>
      </div>
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
    <div class="message-window-block">
      <MessageWindow :messages="messages" />
    </div>
  </div> -->
</template>

<script>
// import Pagination from '@/components/Pagination'
// import Button from '@/components/Button'
import MessageWindow from '@/components/messageWindow'
export default {
  components: {
    // Button,
    // Pagination,
    MessageWindow
  },
  data () {
    return {
      section: 1
    }
  },
  computed: {
    messages () {
      // const messages = [
      //   '当サイトにご訪問頂き、ありがとうございます。\n「さみだれ すずか」と申します。\n' +
      //   'ですが、Internet ExplorerやFirefoxでは「overflow-wrap」のサポートが遅れているところもあるため、' +
      //   '「overflow-wrap」を用いる場合は、念のため「word-wrap」も一緒するべき。',
      //   '趣味について。1つ目はゲームで、得意・好きなジャンルは自動車のレースゲームです。\n' +
      //   '（最近は「原神」にどハマり）・アニメ観賞（fate）・車です。'
      // ]
      const messages = [
        '鋭意制作中、しばし待たれよ。\nしかし最近、スランプに陥って開発が中々スムーズにいかないお'
      ]
      return messages[this.section - 1]
    }
  }
}
</script>

<style scope>
#profile {
  --message-window-block-height: 220px;
  --wrap-pagination-height: 40px;
  --wrap-pagination-margin-height: 12px;
  width: 100vw;
  height: 100vh;
}

/* #profile > .wrap-pagination {
  display: flex;
  justify-content: center;
  margin-top: var(--wrap-pagination-margin-height);
} */

#profile .button-group {
  margin: 0 40px;
  max-width: 400px;
  /* min-width: 200px; */
  width: 100%;
}

#profile .image-block {
  display: flex;
  flex-flow: column;
  height: calc(
    100% - var(--message-window-block-height)
  );
  /* height: calc(
    100% - var(--message-window-block-height)
         - var(--wrap-pagination-height)
         - var(--wrap-pagination-margin-height)
  ); */
  justify-content: space-around;
}

.content_image-window {
  display: flex;
  justify-content: center;
}

.content_image-window > .outline {
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

.content_image-window .icon {
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

#profile > .message-window-block {
  /* align-items: center; */
  display: flex;
  height: var(--message-window-block-height);
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
