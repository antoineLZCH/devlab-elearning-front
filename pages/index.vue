<template>
  <div class="container">
    <Card/>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue';
  import Card from '@/components/CardComponent.vue';
  
  export default Vue.extend({
    components: {Card}
  })
</script>

