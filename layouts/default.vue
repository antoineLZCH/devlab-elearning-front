<template>
  <div class="font-sans antialiased h-screen">
    <Navbar/>
    <div id="main" class="pt-16">
      <Aside/>
      <div id="Content">
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
    margin: 15px 80px 0px;
  }
</style>