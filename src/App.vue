<template>
  <h1>Vue JS</h1>
  <div v-if="showModal">
    <ModalContent :theme="theme" @close="showModal = false">
      <h1>Login Success</h1>
      <p>Welcome Home</p>
    </ModalContent>
  </div>
  <button @click="showModal = true">open modal</button>

  <div v-if="deleteModal">
    <ModalContent theme="delete" @close="deleteModal = false">
      <h1>Are you delete?</h1>
      <p>Sure?</p>
    </ModalContent>
  </div>
  <button @click="deleteModal = true">delete</button>
</template>

<script>
import ModalContent from "./components/ModalContent.vue";

export default {
  components: {
    ModalContent,
  },
  data() {
    return {
      header: "Login Success",
      content: "Welcome to my page",
      theme: "success",
      showModal: false,
      deleteModal: false,
    };
  },
};
</script>

<style scoped>
h1 {
  color: wheat;
}
</style>
