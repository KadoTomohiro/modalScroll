<template>
  <div v-if="open" class="overlay" @click="close">
    <div class="contents" v-scroll-lock="open">
      <slot></slot>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'Modal',
  props: {
    open: {
      type: Boolean,
    },
  },
  methods: {
    close() {
      this.$emit('close')
    },
  },
})
</script>

<style scoped>
.overlay {
  width: 100vw;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.5);
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}
.contents {
  width: 50vw;
  height: 50vh;
  border-radius: 20px;
  padding: 20px;
  background-color: #fff;
  overflow: scroll;
}
</style>
