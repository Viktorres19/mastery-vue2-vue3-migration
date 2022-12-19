<template>
  <div>
    <select
      name="salutation"
      @change="updateSalutation"
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
      @input="updateName"
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
    salutationModifiers: {
      default: () => ({}),
      type: Object
    },
    name: {
      type: String,
      default: ''
    },
    nameModifiers: {
      default: () => ({}),
      type: Object
    },
  },
  setup (props, { emit }) {
    const updateSalutation = event => {
      let val = event.target.value
      if (props.salutationModifiers.capitalize) {
        val = val.toUpperCase()
      }

      emit('update:salutation', val)
    }

    const updateName = event => {
      let val = event.target.value
      if (props.salutationModifiers.capitalize) {
        val = val.charAt(0).toUpperCase() + val.slice(1)
      }

      if (props.salutationModifiers.reverse) {
        val = val.split('').reverse().join('')
      }

      emit('update:name', val)
    }

    return {
      salutations,
      updateSalutation,
      updateName
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