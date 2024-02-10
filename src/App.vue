<template>
  <div class="app">
    <Header />
    <div class="main">
      <ChatWindow ref="chat" />
      <ImageUploadButton :chat="chat" />
    </div>
    <Footer />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import ChatWindow from "./components/ChatWindow.vue";

export default defineComponent({
  name: "App",
  components: {
    Header,
    Footer,
    ChatWindow
  },
  setup() {
    // Define a ref for the chat component
    const chat = ref(ChatWindow);
    // Return the ref
    return {
      chat,
    };
  },
});
</script>

<style>
.app {
  @apply min-h-screen flex flex-col;
}

.main {
  @apply flex-1 flex flex-col;
}
</style>
