<template>
  <div>

    <div class="flex justify-center flex-col">

        <form method="POST" :action="action">
          <div class="max-w-sm rounded shadow-lg overflow-hidden p-5">
                <slot name="title"></slot>
              <fields
              label="UserName"
              type="text"
              name="identifiant"
              ></fields>
              <fields
              label="PassWord"
              type="password"
              name="pwd"></fields>
            <div class=" flex justify-between mb-6 flex-row items-center" >
                <input class="shadow bg-uptoblue border-1 border-uptoblue hover:bg-transparent hover:text-uptoblue focus:shadow-outline focus:outline-none text-white font-bold py-2 px-4 rounded cursor-pointer" type="submit" value="Connect">
                
                <a class="inline-block align-baseline font-bold text-sm text-uptoblue" :href="pwdLink">
                    Forgot Password ?
                </a>
                
            </div>
            
          </div>
        </form>
    </div>

 </div>
</template>

<script>

import fields from '~/components/fields.vue'


export default {
  components: {
    fields
  },
  props: {
      action:{
          type:String,
      },
      pwdLink: {
          type:String
      }
  },
  data() {
    return {
    
    }
  },
}

</script>

<style>

</style>
