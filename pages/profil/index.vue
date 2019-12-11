<template>
    <div>
        <h1>Profil</h1>
        <MenuBoutonComponent chemin="../" color="pink" rounded="false">
            <template slot="icon">
                <img src="../../assets/folder.svg">
            </template>
            <template slot="title" color="pink">
                {{redirection}}
            </template>
        </MenuBoutonComponent>
    </div>
</template>

<script>
 import MenuBoutonComponent from '~/components/MenuBoutonComponent.vue'

export default {
  components: {
    MenuBoutonComponent
  },
    data() {
        return {
            redirection:'lessons',

        }
    },
}
</script>

<style>
</style>