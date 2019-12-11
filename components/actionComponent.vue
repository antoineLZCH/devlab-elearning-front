<template>
    <button 
    :class="{styled: button}" 
    class="flex items-center p-2 m-2">
        {{action}}
        <img 
        :src="'_nuxt/assets/' + filename + '.svg'" 
        :alt="filename"
        class="w-10 pl-2">
    </button>
</template>

<script lang="ts">
export default {
    name:'action',
    props: {
        action:{action:String, required: true},
        button:{button:Boolean, required: true},
        filename:{filename:String, required: false}

    } 
}
</script>

<style>
.styled{
    background: pink;
    color: #fff;
    border-radius: 10px;
    outline: transparent
}
</style>