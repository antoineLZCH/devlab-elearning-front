<template>
  <CardComponent card='titre de la card'>
    <div slot="action" class="flex">
      <span :style="{color:tqt}" class="p-3">{{action}}</span>
    </div>
    <div slot="content">
      <img src="../assets/folder.svg" alt="icon_folder"> 
    <MenuBoutonComponent>
        <span slot="icon">{{icon}}</span>
    </MenuBoutonComponent>
    </div>
    <br>
    
  </CardComponent>

</template>

<script>
import CardComponent from '~/components/CardComponent.vue'
import MenuBoutonComponent from '~/components/MenuBoutonComponent.vue'

export default {
  components: {
    CardComponent,
    MenuBoutonComponent
  },
  data() {
    return {
      action: 'dynamique action',
      rounded: true,
      icon: 'button'
    }
  },
}

</script>

<style>

</style>