<script>
import ProjectCard from '../components/ProjectCard.vue';
import AppLoading from '../components/AppLoading.vue';
import ProjectSearch from '../components/ProjectSearch.vue';
import store from '../store';
import axios from 'axios';

export default {
  name: 'ProjectList',
  data() {
    return {
      store,
      loading: false,
      currentPage: 1,
      responseData: {},
      errors: null,
      projects: [],
    };
  },
  components: {
    ProjectCard,
    AppLoading,
    ProjectSearch,
  },
  methods: {
    getProjects() {
      (this.loading = true),
        axios
          .get(this.store.api.baseUrl + this.store.api.apiUrl.projects, {
            params: {
              page: this.currentPage,
              key: this.store.projects.searchKey,
            },
          })
          .then((response) => {
            console.log(response);
            this.responseData = response.data;
          })
          .catch((error) => {
            console.log(error);
            this.responseData.results.data = [];
            this.errors = error.response.data.message;
          })
          .finally(() => {
            this.loading = false;
          });
    },
    nextPage() {
      this.currentPage++;
      this.getProjects();
    },
    prevPage() {
      this.currentPage--;
      this.getProjects();
    },
  },
  created() {
    this.getProjects();
  },
};
</script>

<template>
  <main class="bg-info">
    <div class="container py-3">
      <h1 class="text-center">Elenco dei Progetti</h1>
      <ProjectSearch @search-project="getProjects" />
      <div class="mt-2" v-if="errors">
        <strong>{{ errors }}</strong>
      </div>
      <AppLoading v-if="loading" />
      <div class="row mt-4" v-else>
        <div
          class="col col-md-4 g-4"
          v-for="project in responseData.results?.data"
        >
          <ProjectCard :project="project" />
        </div>
        <nav class="my-4">
          <ul class="d-flex justify-content-between list-unstyled">
            <li>
              <button
                class="btn btn-secondary"
                @click="prevPage"
                v-show="responseData.results?.prev_page_url"
              >
                Indietro
              </button>
            </li>
            <li>
              <button
                class="btn btn-primary"
                @click="nextPage"
                v-show="responseData.results?.next_page_url"
              >
                Avanti
              </button>
            </li>
          </ul>
        </nav>
      </div>
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
