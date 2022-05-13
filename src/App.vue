
<template>
  <div id="app">
    <CustomForm/>
  </div>
</template>


<script>
  import CustomForm from '@/components/CustomForm'

  export default {
    components: {
      CustomForm,
    }
  }
</script>

<style>
  #app {
    font-family: Helvetica, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    margin-top: 60px;
    padding: 0;
  }
</style>

