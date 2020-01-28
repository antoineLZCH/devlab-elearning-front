<template>
<nav class="bg-gray-700  mt-0 h-auto fixed w-full z-20 top-0">

        <div class="flex flex-wrap items-center nav_size">
            <div class="flex items-center bg-gray-300 text-center h-full w-48 logo_container">
              <nuxt-link to="/" class="logo">
                <img 
                src="~/assets/img/logo.png" 
                alt="Up2You logo"
                >
              </nuxt-link>
            </div>

            <div class="flex flex-1 md:w-1/3 justify-center md:justify-start text-white px-2">
                <span class="relative w-full">
                    <input type="search" placeholder="Up2You search..." class="w-full bg-gray-800 text-sm text-white transition border border-transparent focus:outline-none focus:border-gray-700 rounded py-1 px-2 pl-10 appearance-none leading-normal">
                    <div class="absolute search-icon" style="top: .5rem; left: .8rem;">
                        <svg class="fill-current pointer-events-none text-white w-4 h-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
                            <path d="M12.9 14.32a8 8 0 1 1 1.41-1.41l5.35 5.33-1.42 1.42-5.33-5.34zM8 14A6 6 0 1 0 8 2a6 6 0 0 0 0 12z"></path>
                        </svg>
                    </div>
                </span>
			</div>

			<div class="flex content-center justify-between md:w-1/3 md:justify-end">

			 <div class="flex items-center h-full text-sm">
            <div class="flex items-center h-full">
              <button v-if="isHidden" @click="isHidden = false" tabindex="-1" class="fixed inset-0 h-full w-full cursor-default"></button>
                <a href="#" class="flex items-center text-white h-full px-4">Notifs</a>
                <div @click="isHidden = !isHidden" class="group relative h-full">
                    <a href="#" class="text-white flex items-center h-full bg-grey-darkest px-4">
                      <img  class="logged_user_picture"
                      src="../assets/img/avatar1.jpg" 
                      alt="users profile picture"
                      >
                      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24" class="h-6 w-6 text-grey-darker fill-current ml-1"><path class="heroicon-ui" d="M15.3 9.3a1 1 0 0 1 1.4 1.4l-4 4a1 1 0 0 1-1.4 0l-4-4a1 1 0 0 1 1.4-1.4l3.3 3.29 3.3-3.3z"/></svg>
                    </a>
                    <div v-show="isHidden" class="absolute pin-r top-full w-48 bg-gray-800">
                        <nuxt-link to="/user/profile" class="block text-left py-3 px-3 text-white hover:bg-gray-900 text-xs">
                            Mon compte
                        </nuxt-link>
                        <nuxt-link to="#" class="block text-left py-3 px-3 text-white hover:bg-gray-900 text-xs">
                            Déconnexion
                        </nuxt-link>
                    </div>
                </div>
            </div>
        </div>

            </div>
        </div>

</nav>


  <!-- <nav>
      <header class="fixed z-50 h-16 w-full bg-gray-700 shadow flex items-center justify-between">
        <div class="flex items-center h-full">
            <div class="flex items-center bg-gray-300 text-center h-full w-48">
              <nuxt-link to="/" class="logo">
                <img 
                src="~/assets/img/logo.png" 
                alt="Up2You logo"
                >
              </nuxt-link>
            </div>
            <div class="flex items-center w-64">
                <form action="" class="w-full h-full px-3 flex items-center">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24" class="h-6 w-6 text-white fill-current"><path class="heroicon-ui" d="M16.32 14.9l5.39 5.4a1 1 0 0 1-1.42 1.4l-5.38-5.38a8 8 0 1 1 1.41-1.41zM10 16a6 6 0 1 0 0-12 6 6 0 0 0 0 12z"/></svg>
                  <input type="search" class="appearance-none bg-gray-700 h-full w-full py-2 px-2 text-white" placeholder="Rechercher...">
                </form>
            </div> 
        </div>
        <div class="flex items-center h-full text-sm">
            <div class="flex items-center h-full">
                <a href="#" class="flex items-center text-white h-full px-4">Notifs</a>
                <div @click="isHidden = !isHidden" class="group relative h-full">
                    <a href="#" class="text-white flex items-center h-full bg-grey-darkest px-4">
                      <img  class="logged_user_picture"
                      src="../assets/img/avatar1.jpg" 
                      alt="users profile picture"
                      >
                      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24" class="h-6 w-6 text-grey-darker fill-current ml-1"><path class="heroicon-ui" d="M15.3 9.3a1 1 0 0 1 1.4 1.4l-4 4a1 1 0 0 1-1.4 0l-4-4a1 1 0 0 1 1.4-1.4l3.3 3.29 3.3-3.3z"/></svg>
                    </a>
                    <div v-show="isHidden" class="absolute pin-r top-full w-48 bg-gray-800">
                        <nuxt-link to="/user/profile" class="block text-left py-3 px-3 text-white hover:bg-gray-900 text-xs">
                            Mon compte
                        </nuxt-link>
                        <nuxt-link to="#" class="block text-left py-3 px-3 text-white hover:bg-gray-900 text-xs">
                            Déconnexion
                        </nuxt-link>
                    </div>
                </div>
            </div>
        </div>
      </header>
  </nav> -->
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  data() {
    return{
      isHidden: false
    }
  }
})
</script>

<style lang="scss">
  a {
    margin: auto;
  }
  img{
    max-width: 100px;
    width: 100%;
    &.logged_user_picture{
      width: 35px;
    }
  }
  .nav_size{
    height: 60px;
  }
  nav .top-full{
    top: 135%;
  }

  @media only screen and (max-width: 475px){
    .logo_container{
      display: none;
    }
  }

</style>