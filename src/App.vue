<template>
  <div id="app">
    <Form />
  </div>
</template>

<script>
import Form from './components/Form.vue'

export default {
  name: 'App',
  components: {
    Form,
  }
}
</script>

<style>
  #app {
    font-family: Arial, Helvetica, sans-serif;
    margin: 0;
    padding: 0;
  }
</style>
