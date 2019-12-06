<template>
  <CardComponent card="titre de la card">
    <div slot="action">
      <p class="p-3">{{action}}</p>
    </div>
    <div slot="content">
      <img src="../assets/folder.svg" alt="icon_folder"> 
    </div>
   
  </CardComponent>
</template>

<script>
import CardComponent from '~/components/CardComponent.vue'

export default {
  components: {
    CardComponent
  },
  data() {
    return {
      action: 'dynamique action',
    }
  },
}

</script>

<style>

</style>