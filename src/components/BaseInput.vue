<template>
  <label>{{ label }}</label>
  <input
    v-bind="{
      ...$attrs,
      onInput: (event) => $emit('update:modelValue', event.target.value)
    }"
    :value="modelValue"
  />
</template>

<script>
export default {
  name: 'BaseInput',
  inheritAttrs: false,
  props: {
    modelValue: {
      type: [String, Number],
      default: ''
    },
    label: {
      type: String,
      default: null
    }
  }
}
</script>

<style scoped>

</style>