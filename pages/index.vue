<template>
  <div>
    <CardComponent card='titre de la card'>
        <template slot="action">
          <actionComponent
           button="true" 
           action="redirection" 
           filename="folder" > 
          </actionComponent> 
        </template>
      <div slot="content">
        <img src="../assets/folder.svg" alt="icon_folder"> 
      </div>
    </CardComponent>
    <MenuBoutonComponent 
      chemin="profil" 
      class="mt-3" 
      rounded="true" 
      color="#65b9fc">
        <template slot="icon">
          <img src="../assets/home.svg">
        </template>
        <template
          slot="title" 
          color="#65b9fc">
          {{redirection}}
        </template>

    </MenuBoutonComponent>
 </div>

</template>

<script>
import CardComponent from '~/components/CardComponent.vue'
import MenuBoutonComponent from '~/components/MenuBoutonComponent.vue'
import actionComponent from '~/components/actionComponent.vue'

export default {
  components: {
    CardComponent,
    MenuBoutonComponent,
    actionComponent
  },
  props: {

  },
  data() {
    return {
      redirection: 'Profil'
    }
  },
}

</script>

<style>

.rounded{
    border-radius: 20px
}
.card{
  background: #65b9fc
}
</style>