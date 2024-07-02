<template>
  <div>
    <button @click="showModal">Open Modal</button>
    <Modal :isVisible="isModalVisible" @close="hideModal" />
  </div>
</template>

<script>
import { ref } from 'vue';
import Modal from './components/Modal.vue';

export default {
  components: {
    Modal,
  },
  setup() {
    const isModalVisible = ref(false);

    const showModal = () => {
      isModalVisible.value = true;
    };

    const hideModal = () => {
      isModalVisible.value = false;
    };

    return { isModalVisible, showModal, hideModal };
  },
};
</script>

<style>
/* Add any additional styles here */
</style>
