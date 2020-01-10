<template>
  <div class="container mx-auto">
    <div class="flex flex-col">
      <h2>Leçons</h2>
      <div class="cards-wrapper flex justify-between my-8">
        <Card v-for="card in cards" :course="card" :key="card.id" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import Card from '@/components/CardComponent.vue';

export default Vue.extend({
  name: 'CoursesPages',
  components: {Card},
  data() {
    return {
      cards: [
        {
          title: "Lorem 1",
          description: "En astrophysique, un trou noir est un objet céleste si compact que l'intensité de son champ gravitationnel empêche toute forme de matière ou de rayonnement de s’en échapper. De tels objets ne peuvent ni émettre, ni diffuser la lumière et sont donc noirs, ce qui en astronomie revient à dire qu'ils sont optiquement invisibles.",
          infos: {
            numberOfLessons: 8,
            numberOfTasks: 40,
            duration: "7 heures"
          }
        },
        {
          title: "Lorem 2",
          description: "En astrophysique, un trou noir est un objet céleste si compact que l'intensité de son champ gravitationnel empêche toute forme de matière ou de rayonnement de s’en échapper. De tels objets ne peuvent ni émettre, ni diffuser la lumière et sont donc noirs, ce qui en astronomie revient à dire qu'ils sont optiquement invisibles.",
          infos: {
            numberOfLessons: 6,
            numberOfTasks: 22,
            duration: "2 heures"
          }
        },
        {
          title: "Lorem 3",
          description: "En astrophysique, un trou noir est un objet céleste si compact que l'intensité de son champ gravitationnel empêche toute forme de matière ou de rayonnement de s’en échapper. De tels objets ne peuvent ni émettre, ni diffuser la lumière et sont donc noirs, ce qui en astronomie revient à dire qu'ils sont optiquement invisibles.",
          infos: {
            numberOfLessons: 12,
            numberOfTasks: 14,
            duration: "8 heures"
          }
        }
      ]
    }
  }
})
</script>

<style lang="scss" scoped>

</style>