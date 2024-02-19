<script>
export default {
  name: 'NotFound',
};
</script>

<template>
  <div class="text-center py-4 container container-max">
    <h2 class="text-uppercase">Spiacenti pagina non trovata</h2>
    <h6 class="mt-3">
      <router-link :to="{ name: 'projects' }" class="text-decoration-none"
        >Torna ai Progetti</router-link
      >
    </h6>
  </div>
</template>

<style scoped lang="scss">
.container-max {
  height: 100vh;
}
</style>
