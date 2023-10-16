<template>
  <base-button
      :disabled="isPending"
      :color="color"
      @click.stop.prevent="handleClick"
  >
    <slot />
  </base-button>
</template>

<script>
import BaseButton from './BaseButton.vue'

export default {
  name: 'AsyncButton',
  components: { BaseButton },

  props: {
    color: {
      type: String,
      default: 'primary'
    },

    delayCounter: {
      type: Number,
      required: true
    }
  },

  data () {
    return {
      isPending: false
    }
  },

  methods: {
    async delay(ms) {
      return new Promise(resolve => setTimeout(resolve, ms));
    },

    async handleClick() {
      this.isPending = true;
      console.log(this.delayCounter);
      // Simulate a 2-second delay (and increase each time it is clicked)
      await this.delay(this.delayCounter * 1_000);

      this.isPending = false;
    }
  }
}
</script>