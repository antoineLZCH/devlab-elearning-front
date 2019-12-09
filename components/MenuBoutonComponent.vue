<template>
  <div>
   <button :style="{color: activecolor}" class="block m-auto w-full" :class="{rounded:rounded}"  >
       <slot name="icon" class="p-3"></slot>
   </button>
  </div>
</template>

<script lang="ts">
export default {
    props: {
        rounded: {rounded:Boolean, default: 'square' },
        icon:String, 
        activecolor:String
    },
    data() {
        return {
         activecolor: 'red'   
        }
    },

}
</script>

<style>
.square{
    border-radius: unset
}
.rounded{
    border-radius: 20px
}
</style>