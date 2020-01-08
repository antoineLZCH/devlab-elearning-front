<template>
  <div class="flex flex-row pt-6 items-center justify-around">
    <div class="max-w-sm">
        <img src="../assets/logo.png">
    </div>
    
    <connexion
    action=""
    pwdLink=""
    >
      <template slot="title">
        <h3 class="text-4xl text-center">Connexion</h3>
      </template>
    </connexion>

 </div>
</template>

<script lang="ts">
import Vue, {PropOptions} from 'vue';

import connexion from '~/components/connexion.vue'
import fields from '~/components/fields.vue'

export default {
  components: {
    connexion,
    fields
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
