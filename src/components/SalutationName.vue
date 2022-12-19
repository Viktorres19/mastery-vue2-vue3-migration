<template>
  <div>
    <select name="salutation"
        @change="$emit(
        'update:salutation',
        $event.target.value)"
    >
      <option value="">-</option>
      <option
        v-for="item of salutations"
        :value="item"
        :key="item"
        :selected="salutation === item"
      >
        {{ item }}
      </option>
    </select>
    <input
      @input="$emit('update:name', $event.target.value)"
      :value="name"
      type="text"
      name="name"
    >
  </div>
</template>

<script>
const salutations = [
  'Ms.',
  'Mrs.',
  'Miss',
  'Mx.',
  'Dr.'
]

export default {
  name: 'SalutationName',
  props: {
    salutation: {
      type: String,
      default: ''
    },
    name: {
      type: String,
      default: ''
    }
  },
  setup () {
    return {
      salutations
    }
  }
}
</script>

<style lang="scss" scoped>
div {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}
</style>