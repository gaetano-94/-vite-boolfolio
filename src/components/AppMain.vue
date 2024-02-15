<script>
import ProjectCard from './ProjectCard.vue';
export default {
  name: 'Main',
  props: ['projects'],

  components: {
    ProjectCard,
  },
};
</script>

<template>
  <main class="bg-info">
    <div class="container py-3">
      <h1 class="text-center">Elenco dei Progetti</h1>
      <div class="row mt-4">
        <div class="col col-md-4 g-4" v-for="project in projects"></div>
      </div>
      <ProjectCard />
    </div>
  </main>
</template>

<style scoped lang="scss">
h1 {
  color: green;
  text-transform: uppercase;
}
.card {
  border: 2px solid black;
  background-color: lightgray;
}
</style>
