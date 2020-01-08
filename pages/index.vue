<template>
  <div>
    <CardComponent :card="title_card">
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
          <img class="z-100" src="../assets/home.svg">
        </template>
        <template
          slot="title">
          {{redirection}}
        </template>
    </MenuBoutonComponent>
    <br><br>
  <div class="flex justify-center">
      <form>
        <div class="max-w-sm rounded shoadow-lg overflow-hidden">
            <fields
            label="UserName"
            type="text"
            name="identifiant"
            ></fields>
            <fields
            label="PassWord"
            type="password"
            name="pwd"></fields>
          <div class=" flex justify-center mb-6">
              <input class="shadow bg-purple-500 hover:bg-purple-400 focus:shadow-outline focus:outline-none text-white font-bold py-2 px-4 rounded cursor-pointer" type="submit" value="Connect">
          </div>
        </div>
      </form>
  </div>

 </div>

</template>

<script>
import CardComponent from '~/components/CardComponent.vue'
import MenuBoutonComponent from '~/components/MenuBoutonComponent.vue'
import actionComponent from '~/components/actionComponent.vue'
import fields from '~/components/fields.vue'

export default {
  components: {
    CardComponent,
    MenuBoutonComponent,
    actionComponent,
    fields
  },
  props: {
  },
  data() {
    return {
      redirection: 'Profil',
      title_card: 'titre de la card'
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
