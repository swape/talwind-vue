<template>
  <div class="main">
    <h1 class="text-2xl mb-3">Tailwind vue demo</h1>

    <div class="flex flex-wrap gap-4">
      <TailwindButton label="Nullstill" @action="clear" />
      <input type="text" name="text" class="ml-2" v-model="textValue" />
    </div>

    <div class="box mt-8">{{ textValue }}</div>
    <div class="box">{{ textValueReverse }}</div>
    <div class="box">{{ wordCount }} tegn</div>
  </div>
</template>
<script>
import TailwindButton from '@/components/TailwindButton'

export default {
  name: 'App',
  components: { TailwindButton },
  data() {
    return {
      textValue: 'Test'
    }
  },
  computed: {
    textValueReverse() {
      return this.textValue
        .split('')
        .reverse()
        .join('')
    },
    wordCount() {
      return this.textValue.split('').length
    }
  },
  methods: {
    clear() {
      this.textValue = ''
    }
  }
}
</script>
<style>
.main {
  @apply container mx-auto p-10;
}

.box {
  @apply my-2 bg-yellow-50 rounded-md ring-1 ring-blue-300 py-1 px-4;
  min-height: 33px;
}
</style>
