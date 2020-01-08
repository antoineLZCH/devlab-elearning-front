<template>
<div class="md:flex md:items-center mb-6">
      <div class="md:w-1/3">
           <label :for="name">{{label}}</label>
      </div>
       <div class="md:w-2/3">
           <input :type="type" :name="name" :id="name"
           class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-purple-500">
       </div>
</div>
</template>

<script lang="ts">
export default {
  name:'formulaire', 
  props: {
    label:String,
    type: String,
    name:String
  },
  data() {
    return {
    }
  },
}

</script>

<style>

</style>