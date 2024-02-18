<script>
export default {
  name: 'NotFound',
};
</script>

<template>
  <div class="text-center py-4 container">
    <h2 class="text-uppercase">Spiacenti pagina non trovata</h2>
    <h6>
      <router-link :to="{ name: 'home' }" class="text-decoration-none"
        >Torna all'home page</router-link
      >
    </h6>
  </div>
</template>

<style scoped lang="scss"></style>
