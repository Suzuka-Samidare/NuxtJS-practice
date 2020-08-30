<template>
  <div class="message-window-root">
    <div class="messanger">
      <span>*Suzuka-Samidare</span>
    </div>
    <div class="message-container">
      <div class="content">
        ですが、Internet ExplorerやFirefoxでは「overflow-wrap」のサポートが遅れているところもあるため、「overflow-wrap」を用いる場合は、念のため「word-wrap」も一緒に記載しておいたほうがよいでしょう。
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scope>
.message-window-root {
  --message-container-height: 200px;
  height: calc(var(--message-container-height) + 32px);
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
  background-color: #525252;
  border: 2px solid #FFFFFF;
  height: var(--message-container-height);
  padding: 10px;
  position: relative;
  top: -2px;
  z-index: 0;
}

.message-container > .content {
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
  word-break: break-word;
}
</style>
