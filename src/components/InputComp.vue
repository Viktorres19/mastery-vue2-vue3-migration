<template>
<!--  vue 2-->
<!--  <input
    :value="email"
    :type="type"
    @input="$emit(
      'input',
      $event.target.value
    )"
  >-->
<!--  vue 3-->
    <input
      :value="modelValue"
      :type="type"
      @input="$emit(
        'update:modelValue',
        $event.target.value
      )"
    >
</template>

<script>
export default {
  name: 'InputComp',
  data() {
    return {
      type: 'input'
    }
  },
  //vue 2
  /*props: {
    email: {
      type: [String, Number],
      default: ''
    }
  }*/
  //vue 3
  props: {
    modelValue: {
      type: [String, Number],
      default: ''
    }
  }
}
</script>

<style scoped>

</style>