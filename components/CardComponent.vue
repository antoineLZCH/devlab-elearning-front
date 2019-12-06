<template>
  <div class="flex justify-center items-center flex-col rounded w-1/3">
    <div class="flex-1 flex justify-between w-full">
      <p class="p-3 text-center">{{card}}</p>
      <slot name="action" class="p-3"></slot>
    </div>
    <div class="flex-1 w-32 w-auto m-1">
      <slot name="content"></slot>
    </div>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "card componement Paul"
    }
  }, 
  props: 
    {card:String}
  }

</script>

<style>
.flex{
  background: #65b9fc
}
</style>