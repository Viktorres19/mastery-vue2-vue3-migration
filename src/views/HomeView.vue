<template>
  <div class="home">
    <SalutationName
      v-model:salutation.capitalize="form.salutation"
      v-model:name.capitaze="form.name"
    />
    <pre>{{ form }}</pre>
  </div>
</template>

<script>
import { reactive } from 'vue'
import SalutationName from '@/components/SalutationName.vue'

export default {
  name: 'HomeView',
  components: {
    SalutationName
  },
  setup () {
    const form = reactive({
      salutation: '',
      name: ''
    })

    return {
      form
    }
  }
}
</script>
