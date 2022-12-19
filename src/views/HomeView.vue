<template>
  <div class="home">
    <BaseInput
      v-model="email"
      @blur="email = 'blurrr@its.cold'"
      label="Email:"
      type="email"
    />

    <pre>{{ email }}</pre>
  </div>
</template>

<script>
import { ref } from 'vue'
import BaseInput from '@/components/BaseInput'

export default {
  name: 'HomeView',
  components: {
    BaseInput
  },
  setup () {
    const email = ref('')

    return {
      email
    }
  }
}
</script>
