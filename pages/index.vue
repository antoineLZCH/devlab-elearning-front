<template>
  <div class="flex flex-col pt-6 items-center justify-around">
    <div class="max-w-sm">
        <img src="../assets/logo.png">
    </div>
    
    <connexion
    action="#"
    pwdLink="#"
    >
      <template slot="title">
        <h3 class="text-4xl font-medium text-center">Connexion</h3>
      </template>
    </connexion>
    <!-- <nuxt-link to="lecons">LECONS</nuxt-link> -->
 </div>
</template>

<script lang="ts">

import connexion from '~/components/connexion.vue'


export default {
  components: {
    connexion

  },
  props: {
  },
  data() {
    return {
 
    }
  },
}

</script>

<style>

</style>
