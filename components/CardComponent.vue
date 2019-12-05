<template>
  <div class="flex justify-center items-center flex-col border-solid border-4 border-gray-600 w-1/3">
    <div class="flex-1 flex justify-between w-full">
      <p class="title p-2">Title</p>
      <slot name="action"></slot>
    </div>
    <div class="flex-1 bg bg-gray-700 w-32 border-solid border-2 border-gray-600 w-auto m-1">
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
  }
}
</script>

<style>

</style>