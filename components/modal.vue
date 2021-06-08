<template>
  <div v-if="open" class="overlay" @click="close">
    <div class="popup">
      <header>overflow: scroll</header>
      <div class="contents overflow" v-scroll-lock="open">
        <slot></slot>
      </div>
    </div>
    <div class="popup">
      <header>overflow: auto</header>
      <div class="contents overflow-auto" v-scroll-lock="open">
        <slot></slot>
      </div>
    </div>
    <div class="popup">
      <header>overflow-y: scroll</header>
      <div class="contents overflow-y" v-scroll-lock="open">
        <slot></slot>
      </div>
    </div>
    <div class="popup">
      <header>overflow-y: auto</header>
      <div class="contents overflow-y-auto" v-scroll-lock="open">
        <slot></slot>
      </div>
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
header {
  font-size: 2rem;
  border-bottom: 1px solid #555;
  padding-bottom: 0.2em;
}
.overlay {
  width: 100vw;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.5);
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  justify-content: space-around;
  align-items: center;
  flex-wrap: wrap;
}
.popup {
  width: 40vw;
  border-radius: 20px;
  padding: 20px;
  background-color: #fff;
}
.contents {
  height: 30vh;
}

.overflow {
  overflow: scroll;
}

.overflow-auto {
  overflow: auto;
}

.overflow-y {
  overflow-y: scroll;
}

.overflow-y-auto {
  overflow-y: auto;
}
</style>
