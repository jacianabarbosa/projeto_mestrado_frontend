<template>
  <div class="chat-container">
    <div class="chat-display">
      <div v-for="message in messages" :key="message.content" class="message">
        <div class="icon icon-sm">
          <i
            :class="message.role === 'user' ? 'fas fa-user' : 'fas fa-robot'"
          ></i>
        </div>
        <div class="text-content">
          <strong class="sender-name">{{
            message.role === "user" ? "You" : "D-creea IA"
          }}</strong>
          <p>{{ message.content }}</p>
        </div>
      </div>
    </div>
    <chat-input @send-message="handleNewMessage" />
  </div>
</template>

<script>
import ChatInput from "./ChatInput.vue"; // Ajuste o caminho conforme necessário

export default {
  components: {
    ChatInput,
  },
  props: {
    messages: Array,
  },
  methods: {
    handleNewMessage(newMessage) {
      this.$emit("sendMessage", newMessage);
    },
  },
};
</script>

<style scoped>
.chat-container {
  border-radius: 2%;
  max-width: 70%;
  margin: auto;
  background-color: #f5f5f5; /* Background do chat */
}

.chat-display {
  flex: 1;
  overflow-y: auto;
  padding: 20px;
  height: 500px; /* Definindo um limite para a altura */
}

.message {
  display: flex;
  align-items: flex-start;
  margin-bottom: 20px;
}

.icon {
  width: 45px;
  height: 45px;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #ccc;
  margin-right: 10px;
}

.icon-sm {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #ccc;
  margin-right: 10px;
}

.fas {
  color: #444;
  font-size: 1rem;
}

.text-content {
  flex: 1;
  word-break: break-word;
  text-align: left;
}

.sender-name {
  display: block;
  color: #333;
  margin-bottom: 5px;
}

p {
  margin: 0;
}
</style>
