<template>
  <span class="image-box">
    <img src="~/assets/language.svg" alt="" />
    <small><slot></slot></small>
  </span>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'ImageBox',
})
</script>

<style scoped>
.image-box {
  border: 1px solid #333;
  border-radius: 5px;
  padding: 0.5em;
  display: flex;
  flex-direction: column;
  margin: 1em;
}
</style>
