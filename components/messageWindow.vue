<template>
  <div class="message-window-root">
    <div class="messanger">
      <span>*Suzuka-Samidare</span>
    </div>
    <div id="message" class="message-container" @click="nextText()">
      <client-only placeholder="Loading...">
        <div v-if="isShow">
          <span
            v-for="(t, index) in divideMessages[page]"
            :key="index"
            class="message-span"
            :style="{animationDelay: index*30+'ms'}"
          >
            {{ t }}
          </span>
        </div>

        <!-- <div v-if="isShow">
          <span
            style="white-space:pre-line;"
            v-text="testText"
          />
        </div> -->

        <!-- <div
          v-for="(mes, mesIndex) in divideMessages"
          :key="mesIndex"
        >
          <div v-if="isShow && mesIndex === page">
            <span>{{ mesIndex }}</span>
            <span
              v-for="(t, tIndex) in mes"
              :key="tIndex"
              class="message-span"
              :style="{animationDelay: tIndex*30+'ms'}"
              v-text="t"
            />
          </div>
        </div> -->
      </client-only>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    messages: {
      type: String,
      default: ''
    }
  },
  data (vm) {
    return {
      testText: 'aaaaaaaaaa\nbbbbbbb',
      isShow: true,
      page: 0,
      clientWidth: null,
      divideMessages: []
    }
  },
  computed: {
    divideMessagesLength () {
      return this.divideMessages.length
    }
  },
  watch: {
    messages: {
      async handler () {
        this.isShow = await false
        await this.arrangeMessages()
        this.isShow = await true
      }
    }
  },
  async mounted () {
    this.clientWidth = await document.getElementById('message').clientWidth
    await this.arrangeMessages()
  },
  methods: {
    rowLengthLimit () {
      const rowLength = Math.floor(this.clientWidth / 20)
      const allLength = rowLength * 5
      return allLength
    },
    arrangeMessages () {
      if (process.client) {
        const periodSplitMessages = this.messages.split(/(?<=。)/g) // 肯定的後読み
        // const periodSplitMessages = this.messages.split(/\\ret/g)
        const rowLengthLimit = this.rowLengthLimit()
        const arrangeMessages = periodSplitMessages.map((str) => {
          if (str.length > rowLengthLimit) {
            const commaSplitMessages = str.split(/(?<=、)/g)
            const returnArr = []
            let pushMessage = ''
            for (let i = 0; i < commaSplitMessages.length; i++) {
              if (pushMessage.length + commaSplitMessages[i].length <= rowLengthLimit) {
                pushMessage += commaSplitMessages[i]
                if (i + 1 === commaSplitMessages.length) {
                  returnArr.push(pushMessage)
                  pushMessage = ''
                }
              } else {
                returnArr.push(pushMessage)
                pushMessage = ''
              }
            }
            return returnArr
          } else {
            return str
          }
        })
        this.divideMessages = arrangeMessages.flat()
        console.log(this.divideMessages)
      } else {
        this.divideMessages = ['Loading...']
      }
    },
    async nextText () {
      this.isShow = await false
      if (this.page < this.divideMessages.length - 1) {
        this.page += await 1
      } else {
        await this.$router.push('menu')
        this.page = await 0
      }
      this.isShow = await true
    }
  }
}
</script>

<style scope>
.message-window-root {
  /* --messanger-height: 40px; */
  --message-container-height: 174px;
  /* height: calc(var(--message-container-height) + var(--messanger-height)); */
}

.messanger {
  border-left: 2px solid #FFFFFF;
  border-right: 2px solid #FFFFFF;
  border-top: 2px solid #FFFFFF;
  border-radius: 10px 10px 0 0;
  background-color: #525252;
  display: inline-block;
  padding: 5px 8px 5px;
  position: relative;
  z-index: 1;
}

.messanger > span {
  border-bottom: 2px solid #FFFFFF;
  color: #FFFFFF;
  padding-bottom: 3px;
  z-index: 100;
}

.message-container {
  --message-container-border: 2px;
  --message-container-padding: 10px;
  background-color: #525252;
  border: var(--message-container-border) solid #FFFFFF;
  height: var(--message-container-height);
  padding: var(--message-container-padding);
  position: relative;
  top: -2px;
  /* width: calc(
    100vw - (var(--message-container-border) * 2)
          - (var(--message-container-padding) * 2)
  ); */
  width: calc(1100px - 10px - 10px);
  z-index: 0;
  color: #FFFFFF;
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  overflow-x: hidden;
  overflow-y: scroll;
  overflow-wrap: break-word;
  -ms-overflow-style: none; /* IE、Edgeでスクロールバーを非表示 */
}
.message-container::-webkit-scrollbar {
    display:none;
}
@media screen and (max-width: 1100px) {
  .message-container {
    width: calc(100vw - 10px - 10px);
  }
}

@keyframes text-in {
  0% {
    opacity: 0;
    color: black;
  }
  15% {
    color: black;
  }
}
.message-span {
  display: inline-block;
  animation: text-in .3s cubic-bezier(0.22, 0.15, 0.25, 1.43) 0s backwards;
  /* opacity: 0; */
}
/* .message-span-fadeIn {
  opacity: 1;
} */

/* .message-container > .content {
  color: #FFFFFF;
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  height: 100%;
  width: 100%;
  overflow-x: hidden;
  overflow-y: scroll;
  overflow-wrap: break-word;
} */
</style>
