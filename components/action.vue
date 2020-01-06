<template>

  <div class="w-14 m-5" @click="handleClick">
      <slot></slot>

  </div>


</template>

<script>
  export default {
    name: 'actionComponent',
    methods : {
      handleClick : function() {
        alert('Clicked Me ! ')

      }
    }
  }
</script>

<style scoped>

</style>
