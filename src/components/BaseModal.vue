<template>
  <Teleport to="body">
    <Transition name="modal-outer">
      <div
        v-show="modalActive"
        class="fixed inset-0 bg-black bg-opacity-30 flex items-center justify-center px-4"
      >
        <Transition name="modal-inner">
          <div
            v-if="modalActive"
            class="bg-teal-600 rounded-xl shadow-lg w-full max-w-md"
          >
            <div class="p-6 bg-orange-50 rounded-t-xl">
              <slot />
            </div>
            <div class="p-4 flex justify-end">
              <button
                class="bg-orange-500 text-white py-2 px-6 rounded-lg hover:bg-orange-600 transition duration-300"
                @click="$emit('close-modal')"
              >
                Close
              </button>
            </div>
          </div>
        </Transition>
      </div>
    </Transition>
  </Teleport>
</template>

<script setup>
defineEmits(["close-modal"]);
defineProps({
  modalActive: {
    type: Boolean,
    default: false,
  },
});
</script>

<style scoped>
.modal-outer-enter-active,
.modal-outer-leave-active {
  transition: opacity 0.3s ease;
}

.modal-outer-enter-from,
.modal-outer-leave-to {
  opacity: 0;
}

.modal-inner-enter-active {
  transition: all 0.3s ease;
}

.modal-inner-leave-active {
  transition: all 0.3s ease;
}

.modal-inner-enter-from {
  opacity: 0;
  transform: scale(0.9);
}

.modal-inner-leave-to {
  transform: scale(0.9);
  opacity: 0;
}
</style>