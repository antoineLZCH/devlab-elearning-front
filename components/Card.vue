<template>

  <div id="container .text-lg">
    <h1>{{ post }}</h1>
  </div>

</template>

<script type="text/javascript">
  export default {
    name: 'Card',
    props : ['post']
  }
</script>

<style scoped>

  h1 {
    text-align: center;
    font-size: 42px;
  }



</style>
