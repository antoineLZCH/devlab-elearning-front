<template>
  <div class="bg-gray-700 font-sans leading-normal tracking-normal mt-12 sized_top">
    <Navbar/>
    <div class="flex flex-col md:flex-row bg-gray-300">
      <Aside/>
      <div id="Content" class="main-content flex-1 bg-gray-100 mt-12 md:mt-2 pb-24 md:pb-5">
        <nuxt/>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from '~/components/Navbar'
import Aside from '~/components/Aside'

export default {
  components: {
    Navbar,
    Aside
  }
}
</script>

<style lang="scss">
  #Content{
    padding: 15px 80px 0px;
  }

  @media only screen and (max-width: 770px){
    #Content{
      margin-bottom: 55px;
      padding: 15px 22px 0px;
    }
    .sized_top.mt-12{
      margin-top: 13px;
    }
  }
</style>