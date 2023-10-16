<template>
  <div>
    <header>
      <!-- Header content goes here -->
      <h1>My App Header</h1>
    </header>

    <!-- Slot to render main content -->
    <slot></slot>

    <footer>
      <!-- Footer content goes here -->
      <p>My App Footer</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: "BaseLayout"
}
</script>

<style scoped>

</style>