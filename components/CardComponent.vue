<template>
    <div class="card rounded shadow-lg">
        <img src="http://lorempixel.com/400/200/" class="w-full">
        <div class="px-6 py-4">
            <h3 class="font-bold text-xl mb-2">{{ course.title }}</h3>
            <p class="text-gray-700 text-base">
                 {{ course.description }}
            </p>
        </div>
    </div>
</template>

<script lang="ts">
import Vue, {PropOptions} from 'vue';
import ICourse from '@/interfaces/ICourse';

export default Vue.extend({
    name: 'Card',

    props: {
        course: {
          type: Object,
          required: true
        } as PropOptions<ICourse>
    },

    data() {
        return {

        }
    }
})

</script>

<style lang="scss">
.card {
    max-width: 400px;
    img {
        object-fit: cover;
    }
}
</style>
