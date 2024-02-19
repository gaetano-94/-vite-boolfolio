<script>
import store from '../store';

export default {
  name: 'ProjectSearch',
  data() {
    return {
      store,
    };
  },
  emits: ['searchProject'],
  methods: {
    search() {
      this.$emit('searchProject');
    },
  },
};
</script>

<template>
  <section id="project-search">
    <form action="" @submit.prevent="search">
      <div class="form-floating mb-2 mt-4">
        <input
          type="text"
          class="form-control"
          id="search-key"
          placeholder="Cerca nei Progetti"
          v-model="store.project.searchKey"
        />
        <label for="search-key">Cerca nei Progetti</label>
      </div>
      <button class="btn btn-primary">Cerca</button>
    </form>
  </section>
</template>
