<template>
  <div>
    <ul>
      <li v-for="n in list" :key="n" @click="onClick(n)">
        {{ n }}
      </li>
    </ul>
    <Modal :open="open" @close="onModalClose">
      <p v-for="m in modalContents">
        {{ m }}
      </p>
    </Modal>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Modal from '~/components/modal.vue'

export default Vue.extend({
  components: {
    Modal,
  },
  data() {
    return {
      open: false,
      number: 0,
    }
  },
  computed: {
    list(): number[] {
      return [...Array(200).keys()]
    },
    modalContents(): number[] {
      return [...Array(200).keys()].map(() => this.number)
    },
  },
  methods: {
    onClick(n: number) {
      this.number = n
      this.open = true
    },
    onModalClose() {
      this.open = false
    },
  },
})
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
li {
  border: 1px solid #aaa;
  border-radius: 5px;
  color: #526488;
  margin: 1em;
  padding: 1em;
}
li:hover {
  cursor: pointer;
}
</style>
