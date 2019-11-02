<template>
  <div class="container">
    <div>
      <h1>Hello from <span>{{ name }}</span>.</h1>
      <p><NLink to="/" class="">Back home</NLink></p>
    </div>
  </div>
</template>

<script>
export default {
  asyncData() {
    return {
      name: (process.server ? 'server' : 'client')
    }
  }
}
</script>

<style scoped>

</style>
