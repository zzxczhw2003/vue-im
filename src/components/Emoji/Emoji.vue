<template>
  <div class="emoji" v-show="emojiVisible">
    <i v-for="item in 56" class="emoji-item" :class="'emoji' + item" @click="handleSendEmoji(item)"></i>
  </div>
</template>
<script>
  export default {
    name: 'emoji',
    data () {
      return {
        emojiVisible: false
      }
    },
    methods: {
      handleSendEmoji (index) {
        this.$parent.handleEmojiVisible(false)
        this.$parent.handleSendEmoji(index)
      }
    }
  }
</script>
<style lang="scss">
.emoji {
  position: absolute;
  top: -220px;
  left: -200px;
  width: 400px;
  height: 200px;
  overflow: auto;
  background: #fff;
  padding: 10px;
  border-radius: 10px;
  box-shadow: 0 2px 2px 0 rgba(0, 0, 0, 0.14), 0 3px 1px -2px rgba(0, 0, 0, 0.2), 0 1px 5px 0 rgba(0, 0, 0, 0.12);
  .emoji-item:hover {
    background-color: #c5c5c5;
    border-radius: 5px;
    cursor: pointer;
  }
}
.emoji-item {
  display: inline-block;
  width: 26px;
  height: 26px;
  background-size: 30px;
  background-repeat: no-repeat;
  background-position: center;
  padding: 5px;
}
.user .emoji-item {
  width: 18px;
  height: 18px;
  background-size: 20px;
  padding: 0;
}
@for $i from 0 through 55 {
  .emoji#{$i} { background-image: url(./emoji/#{$i}.png) }
}
</style>