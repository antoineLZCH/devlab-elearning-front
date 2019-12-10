<template>
  <div>
   <button :style="{background: color}" class="block mr-auto w-20 outline-none p-3" :class="{rounded:rounded}"  >
       <slot name="icon"></slot>
   </button>
  </div>
</template>

<script lang="ts">
export default {
    props: {
        rounded: {rounded:Boolean, default: false },
        color:{color:String, default: '#fff'},
        icon:String,
    },

}
</script>

<style>

</style>