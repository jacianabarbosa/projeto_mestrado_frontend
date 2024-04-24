<template>
  <div class="home-view">
    <chat-display :messages="messages" @sendMessage="handleNewMessage" />
  </div>
</template>

<script>
import ChatDisplay from "@/components/ChatDisplay.vue";
import axios from "axios";

export default {
  components: {
    ChatDisplay,
  },
  data() {
    return {
      messages: [
        {
          role: "gpt",
          content: `Olá, sou a D-creea IA e estou aqui para ajudá-lo a criar seu jogo!
            Me informe as características do seu jogo que irei começar a criação!`,
        },
      ],
    };
  },
  methods: {
    handleNewMessage(newMessage) {
      this.messages.push({ role: "user", content: newMessage });

      const messagesToSend = this.messages.slice(1);

      axios
        .post("http://localhost:8000/ask-gpt", { messages: messagesToSend })
        .then((response) => {
          this.messages.push({
            role: "gpt",
            content: response.data.response,
          });
        })
        .catch((error) => {
          console.error("Erro ao enviar mensagem:", error);
        });
    },
  },
};
</script>

<style>
.home-view {
  display: flex;
  flex-direction: column;
  height: 100%;
}
</style>
