<template>
  <p>THIS IS MY HOME PAGE</p>

  <BaseButton color="primary">Primary Button</BaseButton>
  <BaseButton color="warn" :disabled="true">Disabled Button</BaseButton>
  <BaseButton color="danger">Danger Button</BaseButton>
  <AsyncButton :delayCounter="counter" color="primary" @click.native="counter++">Click me (increasing delay)</AsyncButton>
</template>


<script setup>
  import BaseButton from '@/components/BaseButton.vue';
  import AsyncButton from '@/components/AsyncButton.vue';
  import { ref } from 'vue';
  const counter = ref(2);
</script>

<!--script>

export default {
  name: "HomePage",
  components: {
    BaseButton,
    AsyncButton,
  },
}
</script-->

<style scoped>

</style>