<template>
  <div>
    <a :href="chemin"
       :style="{background: color}"
       class="flex items-center mr-auto w-20 outline-none z-100 btnMenu"
       :class="{rounded:rounded}"
       @mouseover="visible = true;"
       @mouseout="visible = false;"
    >
      <slot name="icon" class="z-100"></slot>
      <transition name="slide">
        <span class="title_hover"
              :style="{background: color}"
              v-if="visible">
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
            rounded: {rounded: Boolean, default: false},
            color: {color: String, default: '#0f0'},
            icon: String,
            redirection: String,
            chemin: String,
        },
        data() {
            return {
                visible: false,

            }
        },
        computed: {

        },

    }
</script>

<style>
  .title_hover {
    padding: 5px 10px 5px 35px;
    margin: -1em;
    border-radius: 10px;
    z-index: 1;
    transition: 0.1s
  }

  .slide-enter-active, .slide-leave-active {
    transition: opacity 1s;
  }

  .slide-enter, .slide-leave-active {
    opacity: 0;
  }

</style>
