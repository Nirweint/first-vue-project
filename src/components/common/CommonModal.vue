<template>
  <div class="modal" v-if="isShowModal" @click.stop="hideModal">
    <div @click.stop class="modal__content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "common-modal",
  props: {
    isShowModal: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    hideModal() {
      this.$emit("update:isShowModal", false);
    },
  },
};
</script>

<style scoped>
.modal {
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  display: flex;
}
.modal__content {
  margin: auto;
  background: #ffffff;
  border-radius: 12px;
  min-height: 300px;
  min-width: 600px;
  padding: 20px;
}
</style>
