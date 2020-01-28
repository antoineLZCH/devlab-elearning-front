<template>
  <aside>
        <div class="bg-gray-300 h-9 fixed bottom-0 mt-12 md:relative md:h-screen w-full md:w-48">
              <button v-if="isHidden" @click="isHidden = false" tabindex="-1" class="fixed inset-0 h-full w-full cursor-default"></button>

            <div class="md:mt-12 md:w-48 md:fixed md:left-0 md:top-0 content-center md:content-start text-left justify-between">
                <ul class=" z-10 list-reset flex flex-row md:flex-col py-0 md:py-3 text-center md:text-left">
                    <li class="flex-1 group">
                        <nuxt-link to="/" class="block py-1 md:py-3 pl-1 align-middle no-underline hover:bg-gray-700">
                          <font-awesome-icon :icon="['fas', 'home']" class="text-gray-700 xl:mr-2 group-hover:text-white" />
                          <span class="pb-1 md:pb-0 text-xs md:text-base text-gray-800 md:text-gray-800 group-hover:text-white block md:inline-block">Accueil</span>
                        </nuxt-link>
                    </li>
                    <li class="flex-1 group">
                      <nuxt-link to="/formation" class="block py-1 md:py-3 pl-0 md:pl-1 align-middle  no-underline hover:bg-gray-700">
                          <font-awesome-icon :icon="['fas', 'book']" class="text-gray-700 group-hover:text-white xl:mr-2"/>
                         <span class="pb-1 md:pb-0 text-xs md:text-base text-gray-800 md:text-gray-800 group-hover:text-white block md:inline-block">Formation</span>
                      </nuxt-link>
                    </li>
                    <ul class="flex-1 z-10 group" @click="isHidden = !isHidden">
                      <li>
                        <div class="block py-1 md:py-3 pl-1 align-middle group-hover:bg-gray-700 no-underline">
                          <font-awesome-icon :icon="['fas', 'user']" class="text-gray-700 xl:mr-2 group-hover:bg-gray-700 group-hover:text-white" />
                            <span class="pb-1 md:pb-0 text-xs md:text-base text-gray-800 group-hover:text-white md:text-gray-800 md:text-white block md:inline-block">Admin</span>
                        </div>
                      </li> 
                      <li class="children_side" v-show="isHidden">
                        <nuxt-link to="/admin/user/list" class="child_side block text-left xl:flex xl:items-center shadow xl:shadow-none py-3 px-3 xl:px-4 border-l-4 border-transparent text-white bg-gray-600 text-xs hover:bg-gray-800">
                          Utilisateurs
                        </nuxt-link>
                        <nuxt-link to="/admin/formation/formations" class="child_side block text-left xl:flex xl:items-center shadow xl:shadow-none py-3 px-3 xl:px-4 border-l-4 border-transparent text-white bg-gray-600 text-xs hover:bg-gray-800">
                          Gestion Formations
                        </nuxt-link>
                      </li>
                    </ul>
                </ul>
            </div>

</div>
  </aside>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  data() {
    return{
      isHidden: false,
      colorNav: false
    }
  }
})
</script>

<style lang="scss">

#main {
  display: grid;
  grid-template-columns: 6rem auto;
}

ul li div{
  cursor: pointer;
}



@media (min-width: 1200px) { 
  
  #main { grid-template-columns: 12rem auto; }
}

.nuxt-link-exact-active:not(.logo){
  background-color: #4a5568;
  &.child_side{
    background-color: #1a202c;
  }
  & > *{
    color: white;
  }
}

a {
  text-decoration: none;
}

.pt-16 {
  padding-top: 4rem;
}


.top-full { top: 100%; }
.left-full { left: 100%; }


@media (min-width: 1200px) {
  .xl\:pin-none { left: auto; }

}

.group:hover{
  background-color: #4a5568;
}

.group:hover .group-hover\:block {
  display: block;
}



@media only screen and (max-width: 764px){
  .children_side{
    position: absolute;
    top: -84px;
    width: 100%;
  }
}

@media only screen and (max-width: 399px){
  .children_side{
    top: -102px;
    width: initial;
  }
}
</style>