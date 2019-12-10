<template>
  <div>
   <a   :href="chemin"
        :style="{background: color}" 
        class="flex items-center mr-auto w-20 outline-none z-10" :class="{rounded:rounded}"
        @mouseover="hoverIn()"
        @mouseout="hoverOut()"
        >
       <slot name="icon"></slot>
       <transition name="slide">
        <span class="title_hover"
             :style="{background: color,}"
             v-if="visible" >
           <slot class="p-2" name="title"></slot>
       </span>
       </transition>
   </a>
  </div>
</template>

<script lang="ts">
export default {
    name: 'BtnMenu',
    props: {
        rounded: {rounded:Boolean, default: false },
        color:{color:String, default: '#fff'},
        icon:String,
        redirection:String,
        chemin:String
    },
    data() {
        return{
            visible: true
        }
    },
    methods: {
        hoverIn() {
            this.visible = true
        },
        hoverOut() {
            this.visible = false
        },
    }

}
</script>

<style>
.title_hover{
    padding:5PX 10px 5px 25px;
    border-radius: 10px;
    z-index: 1;
    transition: 0.1s
}
.slide-enter-active  {
    transition: opacity 1s;
}
.slide-enter{
    /* transform:translateX(-10px); */
    opacity: 0;
}
</style>