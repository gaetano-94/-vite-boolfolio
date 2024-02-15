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
  <main>
    <div class="container py-3 text-uppercase">
      <h1 class="text-center">Elenco dei Progetti</h1>
      <ProjectCard />
    </div>
  </main>
</template>

<style scoped lang="scss"></style>
