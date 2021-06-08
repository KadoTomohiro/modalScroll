<template>
  <div class="container">
    <span class="image-box">
      <img src="language.svg" alt="" />
      <small>Static</small>
    </span>
    <span class="image-box">
      <img src="~/assets/language.svg" alt="" />
      <small>Assets</small>
    </span>
    <span class="image-box">
      <img src="~/assets/large.svg" alt="" />
      <small>Large Assets</small>
    </span>
    <ImageBox class="image-box-component">Component</ImageBox>
    <button @click="onClick">表示</button>
    <ImageBox class="image-box-component" v-if="open"
      >Reactive Component</ImageBox
    >
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import ImageBox from '~/components/imageBox.vue'
export default Vue.extend({
  components: {
    ImageBox,
  },
  data() {
    return {
      open: false,
    }
  },
  methods: {
    onClick() {
      this.open = !this.open
    },
  },
})
</script>

<style scoped>
.image-box {
  width: 10em;

  border: 1px solid #333;
  border-radius: 5px;
  padding: 0.5em;
  display: flex;
  flex-direction: column;
  margin: 1em;
}

.image-box-component {
}
</style>
