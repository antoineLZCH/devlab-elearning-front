<template>
  <div class="flex flex-col items-center justify-around">
    
    <connexion
    action="admin/"
    pwdLink="admin/"
    >
      <template slot="title">
        <h1 class="text-4xl font-semibold text-center text-uptoblue">Connexion � Up2You</h1>
      </template>
    </connexion>
    <!-- <nuxt-link to="lecons">LECONS</nuxt-link> -->
 </div>
</template>

<script lang="ts">
  import Vue from 'vue';
  import connexion from '~/components/connexion.vue';
  export default Vue.extend({
  components: {
    connexion

  },
  props: {
  },
  data() {
    return {
 
    }
  },
  })

</script>

