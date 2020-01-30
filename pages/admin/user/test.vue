<template>
  
</template>

<script>
import Vue from 'vue';
import axios from 'axios'

 export default Vue.extend({
  data () {
    return {
      info: null
    }
  },
  mounted () {
    axios
      .get('http://glrd.me:3012/api/admin/users')
      .then(response => (console.log(this.info = response)))
  }
})
</script>