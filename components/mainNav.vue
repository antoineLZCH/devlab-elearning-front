<template>
    <div>
       <div class="fixed top-0 left-0 navClose" :class="{navClose : navClose, navOpen: !navClose}">
            <ul class="flex justify-center bg-gray-200 h-screen w-40">
                <li class="flex justify-center items-center flex-col">
                    <nuxt-link  to="" class="text-medium text-2xl py-6">Accueil</nuxt-link>
                    <nuxt-link to="" class="text-medium text-2xl py-6">Formations</nuxt-link>
                    <nuxt-link to="" class="text-medium text-2xl py-6">Utilisateurs</nuxt-link>
                    <nuxt-link to="" class="text-medium text-2xl py-6">Aide/FAQ</nuxt-link>
                </li>
            </ul>
             <div class="forOpen pa absolute top-0 right-0 bottom-0 flex justify-center items-center w-auto h-auto">
            <button @click="toggle" class="outline-none">
                <i  class="far fa-caret-square-right text-4xl"></i>
            </button>
        </div>
       </div>
       
    </div>
</template>

<script lang="ts">

export default {
  props: {
  },
  data() {
    return {
        navClose: true
    }
  },
  methods: {
      toggle (){
          this.navClose = false
      }
  }
}

</script>

<style>
button:focus{
    outline: none
}
.forOpen{
    margin-right: -2em;
}
.navClose{
    left: -10rem
}
.navOpen{
    left: 0
}
</style>
