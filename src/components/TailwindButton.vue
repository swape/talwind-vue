<template>
  <button type="button" @click="clicked">{{ label }}</button>
</template>
<script>
export default {
  name: 'TailwindButton',
  props: ['label'],
  methods: {
    clicked() {
      this.$emit('action')
    }
  }
}
</script>
<style scoped>
button {
  @apply bg-blue-200 rounded-md ring ring-blue-300 px-3 py-1 hover:bg-blue-400 hover:text-white;
  min-width: 100px;
}
</style>
