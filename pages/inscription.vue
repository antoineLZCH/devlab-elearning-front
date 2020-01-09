<template>
  <div class="flex flex-col items-center justify-around">

    <register
      action="#"
      pwdLink="#"
    >
      <template slot="title">
        <h1 class="text-4xl font-semibold text-center text-uptoblue">Bienvenue !</h1>
      </template>
    </register>

  </div>
</template>



<script>

  import register from '~/components/register.vue'

  export default {
    components: {
      register

    },
    props: {
    },
    data() {
      return {

      }
    },
  }

</script>

<style scoped>

</style>
