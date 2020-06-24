<template>
  <div class="hello">
    <h3>{{ msg }}</h3>
    <div>
      <button v-on:click="openModal">Button</button>
      <div v-show="modal">
        <ChildModal :modal="modal" v-on:childs-event="closeModal"></ChildModal>
      </div>
    </div>
  </div>
</template>

<script>
import ChildModal from './ChildModal.vue'
export default {
  name: 'Parent',
  data () {
    return {
      msg: 'Push a button to open a Modal Window',
      modal: false
    }
  },
  methods: {
    openModal () {
      this.modal = true
    },
    closeModal () {
      this.modal = false
    }
  },
  components: { ChildModal }
}
</script>
