<template>
  <div>
    <h4>Example with page transition</h4>
    <button @click="toggleModal()">Open Modal</button>
    <transition name="fade">
      <div class="modal" v-if="isOpen">
        <button @click="toggleModal()">Close Modal</button>
      </div>
    </transition>
  </div> 
</template>
<script>
import {ref} from 'vue'
export default {
  setup() {
    const isOpen = ref(false)
    const toggleModal = () => {
      return isOpen.value = !isOpen.value
    }

    return {
      isOpen,
      toggleModal
    }
  }
}
</script>
<style scoped>
.modal {
    width: 300px;
    background-color: gray;
    margin: auto;
    text-align: center;
    padding: 64px 48px;
    margin-top: 24px;
}
.fade-enter {
    opacity: 0;
}
.fade-enter-active,.fade-leave-active {
    transition: opacity .5s ease-out;
}
.fade-leave-to {
    opacity: 0;
}
</style>