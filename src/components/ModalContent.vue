<template>
  <div class="backdrop" @click.self="closeModal">
    <div
      class="modal"
      :class="{
        success: theme === 'success',
        danger: theme === 'delete',
      }"
    >
      <slot>default</slot>
    </div>
  </div>
</template>

<script>
export default {
  props: ["theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
.backdrop {
  background-color: rgba(0, 0, 0, 0.2);
  width: 100%;
  height: 100%;
  top: 0;
  position: fixed;
}
.modal {
  color: rgb(226, 43, 43);
  background-color: rgb(13, 164, 205);
  width: 400px;
  margin: 100px auto;
  padding: 20px;
  border-radius: 10px;
}
p {
  font-style: normal;
}
.success {
  background-color: green;
  color: blanchedalmond;
}
.danger {
  background-color: red;
  color: bisque;
}
</style>
