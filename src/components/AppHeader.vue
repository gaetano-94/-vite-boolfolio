<script>
export default {
  name: 'Header',
};
</script>

<template>
  <header class="bg-warning text-white">
    <div class="container d-flex justify-content-between py-2">
      <div><strong>Logo</strong></div>
      <nav>
        <ul class="list-unstyled m-0 p-0 gap-4 d-flex">
          <li>
            <router-link
              :to="{ name: 'home' }"
              class="text-white text-decoration-none"
              ><strong>Home</strong></router-link
            >
          </li>
          <li>
            <router-link
              :to="{ name: 'projects' }"
              class="text-white text-decoration-none"
              ><strong>Projects</strong></router-link
            >
          </li>
          <li>
            <router-link
              :to="{ name: 'about' }"
              class="text-white text-decoration-none"
              ><strong>About</strong></router-link
            >
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<style scoped lang="scss"></style>
