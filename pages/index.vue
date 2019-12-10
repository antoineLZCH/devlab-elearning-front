<template>
 <div>
    <CardComponent card='titre de la card'>
        <span  slot="action" class="p-3">{{action}}</span>
      <div slot="content">
        <img src="../assets/folder.svg" alt="icon_folder"> 
      </div>
    </CardComponent>
    <MenuBoutonComponent chemin="profil" class="mt-3" rounded="true" color="#65b9fc">
        <template slot="icon">
          <img src="../assets/home.svg">
        </template>
        <template slot="title" color="#65b9fc">
          {{redirection}}
        </template>

    </MenuBoutonComponent>
 </div>

</template>

<script>
import CardComponent from '~/components/CardComponent.vue'
import MenuBoutonComponent from '~/components/MenuBoutonComponent.vue'

export default {
  components: {
    CardComponent,
    MenuBoutonComponent
  },
  props: {
    
  },
  data() {
    return {
      action: 'dynamique action',
      redirection: 'Profil',
      icon: 'button'
    }
  },
}

</script>

<style>

.rounded{
    border-radius: 20px
}
.flex{
  background: #65b9fc
}
</style>