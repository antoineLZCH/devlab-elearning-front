<template>
    <div class="card rounded-lg shadow-xl">
        <img src="https://picsum.photos/id/326/400/200" class="w-full">
        <div class="px-6 py-4 flex flex-col">
            <h3 class="font-bold text-xl text-gray-700 mb-0">{{ course.title }}</h3>
            <p class="text-gray-700 my-4">{{ course.description | excerptify(180, '...') }}</p>
            <div class="text-gray-700 text-base flex justify-between infos">
                <p><i class="fas fa-book"></i> {{ course.infos.numberOfLessons }} leçons</p>
                <p><i class="fas fa-tasks"></i> {{ course.infos.numberOfTasks }} tâches</p>
                <p><i class="far fa-clock"></i> {{ course.infos.duration }}</p>
            </div>
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
})

</script>

<style lang="scss" scoped>
  .card {
      max-width: 400px;
      img {
          object-fit: cover;
          border-radius: 0.5rem 0.5rem 0rem 0rem;
      }
  }
</style>
