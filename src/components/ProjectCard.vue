<script>
export default {
  name: 'ProjectCard',
  props: {
    project: Object,
  },
  computed: {
    projectContent() {
      return this.project.content?.substring(0, 100) + '...';
    },
  },
};
</script>

<template>
  <main>
    <div class="card mb-4">
      <div class="card-body card-top">
        <h5 class="card-title">{{ project.title }}</h5>
        <p class="card-text">
          {{ projectContent }}
        </p>
        <router-link
          :to="{ name: 'single-project', params: { slug: project.slug } }"
          class="btn btn-primary"
          >Dettagli Progetto</router-link
        >
      </div>
    </div>
  </main>
</template>

<style scoped lang="scss"></style>
