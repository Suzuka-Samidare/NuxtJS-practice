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
        <div class="content_detail">
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
          <p>Side Job : 765&amp;283Production Producer</p>
          <p>Favorite : Cat, Anime, Game(Racing), Car</p>
        </div>
      </div>
      <div class="message-window-block">
        <MessageWindow :messages="messages" />
      </div>
    </div>
  </div>
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
        '初めましての方は初めまして、ご存知の方はどーも。' +
        'このサイトは鋭意制作中で、動きの無い寂しい画面で申し訳ないけど我慢して欲しい。' +
        '改めて自己紹介、「さみだれ すずか」といいます。' +
        'フロントエンドを主軸に活動しているエンジニアで、現在はVue.jsを使った開発を多くしている。このサイトもnuxt.js出来てますしおすし。' +
        'ちなみに副業で、765プロと283プロのプロデューサーをしている。' +
        '担当アイドルは、765プロが我那覇響、283プロはイルミネーションスターズというユニットだ。どちらもみんなにおすすめしたいアイドルだから、是非応援して欲しい。' +
        '次は好きなものについて。' +
        'まずは猫。' +
        '可愛いが凝縮された皆が知っている動物、可愛いは正義。' +
        '次にアニメ。' +
        'いろんなジャンルを見ているけど、ロボット系は「ガンダム：宇宙世紀シリーズ」、人間戦闘系は「Fate/Stay night」、恋愛系は「彼氏彼女の事情」、「空の境界」が大好き。' +
        'あ、「劇場版アイドルマスター 輝きの向こう側へ」はレジェンド感動作なので絶対見ろ。' +
        'ゲームについて。' +
        '実在する車種が登場するレーシングゲームが特に好き（グランツーリスモとか、Forzaシリーズとか）。' +
        '最近は原神Impactがハマってる、みんなもテイワット大陸のオープンワールドを冒険しようぞ。' +
        '最後に車。' +
        '若者の自動車離れと言われているこの時代、自分もカッコいいと思う車を乗る以外に興味が無いから持っていないんだけど、洗練されたスポーツフォルムを持ったやつとか、ド派手なパワーやトルクのあるやつとか、走りを楽しませることに特化した車はとても好き。' +
        'お気に入りは国産車が、トヨタ：スープラ、外国車がランボルギーニ：アヴェンタドール。' +
        'とりあえず、そんなもんで自己紹介終わり。' +
        'しかし最近、スランプに陥って開発が中々スムーズにいかないお...'
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

#profile > .common-area {
  height: 100%;
  width: 100%;
  padding: var(--bar-height) 10px;
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
  /* flex-flow: column; */
  align-items: center;
  height: calc(
    100% - var(--message-window-block-height)
  );
  width: 770px;
  min-width: 770px;
  margin: auto;
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
  --icon-outline-length: 200px;
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

.icon img {
  width: var(--icon-length);
  height: var(--icon-length);
}

.content_detail {
  border-left: 5px solid #4E504C;
  margin: 8px;
  padding: 8px;
}
.content_detail > .skill-content {
  display: flex;
}
.content_detail > .skill-content ul {
  padding: 0 5px;
}
.content_detail > .skill-content li {
  list-style-type: none;
}

#profile .message-window-block {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: auto;
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
