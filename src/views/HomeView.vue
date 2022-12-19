<template>
  <div class="home">
    <InputComp v-model:modelValue="myInput" />
  </div>
</template>

<script>
import InputComp from "@/components/InputComp.vue";

export default {
  name: 'HomeView',
  components: {
    InputComp
  },
  data() {
    return {
      myInput: ''
    }
  }
}
</script>
