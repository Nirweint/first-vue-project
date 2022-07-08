<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "common-button",
};
</script>

<style scoped>
.btn {
  padding: 10px 15px;
  background: none;
  color: chocolate;
  border: 1px solid teal;
}
</style>
