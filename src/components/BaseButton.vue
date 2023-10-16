<template>
  <button
      :class="[
      'base-button',
      colorClass,  // Apply color-specific class based on the color prop
      { 'animated': !disabled },  // Apply animation if not disabled
    ]"
      :style="{ cursor: disabled ? 'not-allowed' : 'pointer' }"
      :disabled="disabled"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: {
    color: {
      type: String,
      default: 'primary',
      validator: value => ['primary', 'warn', 'danger'].includes(value),
    },
    disabled: {
      type: Boolean,
      default: false,
    },
  },
  computed: {
    colorClass() {
      return `color-${this.color}`;
    },
  },
};
</script>

<style scoped>
.base-button {
  border: none;
  padding: 10px 20px;
  font-size: 1rem;
  cursor: pointer;
  border-radius: 5px;
  transition: all 0.3s ease;
}

.base-button.animated:hover,
.base-button.animated:focus {
  transform: translateY(-3px);
}

.color-primary {
  background-color: darkgreen;
  color: white;
}

.color-warn {
  background-color: grey;
  color: black;
}

.color-danger {
  background-color: red;
  color: white;
}

.base-button[disabled] {
  opacity: 0.6;
}
</style>
