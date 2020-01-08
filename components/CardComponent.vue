<template>
  <div class="flex justify-center items-center flex-col rounded w-1/3 mt-3 card">
    <div class="flex-1 flex justify-between w-full rounded">
      <p class="p-3 m-2 text-center">{{card}}</p>
      <slot name="action" class="p-3"></slot>
    </div>
    <div class="flex-1 w-32 w-auto m-1">
      <slot name="content"></slot>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  name:'Card',
  head() {
    return {
      title: "card componement Paul"
    }
  }, 
  props: {
    card:String 
  },
  data() {
    return {
    }
  },
}

</script>

<style>

</style>