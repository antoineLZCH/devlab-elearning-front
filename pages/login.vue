<template>
<div class="flex flex-col items-center justify-center h-full">
  <img src="~/assets/img/logo.png" alt="Up2You" class="mb-8">
  <form class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 form">
    <div class="mb-4">
      <label class="block text-gray-700 text-sm font-bold mb-2" for="username">
        Email
      </label>
      <input class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" id="email" type="text" placeholder="Email" v-model="email">
    </div>
    <div class="mb-6">
      <label class="block text-gray-700 text-sm font-bold mb-2" for="password">
        Password
      </label>
      <input class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline" id="password" type="password" placeholder="*****" v-model="password" :class="{'border-red-500': isError}">
      <p class="text-red-500 text-xs italic" v-if="isError">Please choose a password.</p>
    </div>
    <div class="flex items-center justify-between">
      <button class="bg-gray-500 hover:bg-gray-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline" type="button">
        Sign In
      </button>
      <a class="inline-block align-baseline font-bold text-sm text-gray-500 hover:text-gray-800" href="#">
        Forgot Password?
      </a>
    </div>
    <div class="mt-8 text-center">
      <nuxt-link to="/register" class="mx-auto w-full font-bold text-gray-500 hover:text-gray-700">You don't have an account ?</nuxt-link>
    </div>
  </form>
  <p class="text-center text-gray-500 text-xs">
    &copy;2020 Up2You. All rights reserved.
  </p>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import IUser from '@/interfaces/IUser';

export default Vue.extend({
  layout: 'default',
  data() {
    return {
      email: '',
      password: '',
      isError: false
    }
  }
})
</script>

<style lang="scss" scoped>
  .form {
    width: 450px;
  }
  a {
    margin: initial;
  }
</style>
