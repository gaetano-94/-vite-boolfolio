<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';
import axios from 'axios';

export default {
  name: 'Container',
  data() {
    return {
      projects: [],
      baseUrl: 'http://127.0.0.1:8000',
      apiUrl: {
        projects: '/api/projects',
      },
    };
  },
  components: {
    AppHeader,
    AppMain,
    AppFooter,
  },
  methods: {
    getProjects() {
      axios
        .get(this.baseUrl + this.apiUrl.projects)
        .then((response) => {
          console.log(response);
          this.projects = response.data.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
  created() {
    this.getProjects();
  },
};
</script>

<template>
  <AppHeader />
  <AppMain :projects="projects" />
  <AppFooter />
</template>

<style scoped lang="scss"></style>
