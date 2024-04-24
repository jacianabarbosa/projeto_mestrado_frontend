<template>
  <div class="chat-input">
    <input
      v-model="inputText"
      @keyup.enter="send"
      placeholder="Type a message..."
    />
    <button @click="send">Send</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputText: "",
    };
  },
  methods: {
    send() {
      if (this.inputText.trim()) {
        this.$emit("sendMessage", this.inputText);
        this.inputText = "";
      }
    },
  },
};
</script>

<style>
.chat-input {
  display: flex;
  padding: 20px;
  height: 40px;
}
.chat-input input {
  flex: 1;
  margin-right: 10px;
}
.chat-input button {
  width: 100px;
}
</style>
