<template>
  <div class="font-sans antialiased h-screen">
    <Navbar/>
    <div id="main" class="pt-16">
      <Aside/>
      <div id="Content">
        <div class="w-full bgImg overflow-hidden flex justify-center items-center">
            <div class="relative">
                <img src="../../assets/img/chess.jpg" alt="person_playing_chess" class=" mt-5">
                <div class="absolute title font-bold text-4xl text-white w-2/3 h-auto">
                    <h3>Augmenter les ventes de votre PME B2B</h3>
                </div>
            </div>
        </div>
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
.bgImg{
    height:22rem
}
.title{
    top:38%;
    left:10%
}

</style>