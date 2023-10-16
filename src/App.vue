<!-- template of file src/App.vue -->
<template>
  <BaseLayout>
    <HomePage>
    </HomePage>
  </BaseLayout>
</template>

<script>
import BaseLayout from '@/components/pages/BaseLayout.vue';
import HomePage from "@/components/pages/HomePage.vue";
export default {
  components: {
    BaseLayout,
    HomePage,
  },
};
</script>


<!-- do not remove the <script /> markup -->