<script>
export default {
  name: 'AppLoading',
};
</script>

<template>
  <div class="text-center">
    <h4>Caricamento in corso...</h4>
    <div class="spinner-grow text-primary" role="status">
      <span class="visually-hidden">Loading...</span>
    </div>
    <div class="spinner-grow text-secondary" role="status">
      <span class="visually-hidden">Loading...</span>
    </div>
    <div class="spinner-grow text-success" role="status">
      <span class="visually-hidden">Loading...</span>
    </div>
    <div class="spinner-grow text-danger" role="status">
      <span class="visually-hidden">Loading...</span>
    </div>
    <div class="spinner-grow text-warning" role="status">
      <span class="visually-hidden">Loading...</span>
    </div>
    <div class="spinner-grow text-info" role="status">
      <span class="visually-hidden">Loading...</span>
    </div>
    <div class="spinner-grow text-light" role="status">
      <span class="visually-hidden">Loading...</span>
    </div>
    <div class="spinner-grow text-dark" role="status">
      <span class="visually-hidden">Loading...</span>
    </div>
  </div>
</template>

<style scoped lang="scss"></style>
