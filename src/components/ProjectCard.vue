<script>
export default {
  name: 'ProjectCard',
  props: {
    project: Object,
  },
};
</script>

<template>
  <main>
    <div class="card">
      <div class="card-body card-top">
        <h5 class="card-title">{{ project.title }}</h5>
        <p class="card-text">
          {{ project.content }}
        </p>
      </div>
    </div>
  </main>
</template>

<style scoped lang="scss"></style>
