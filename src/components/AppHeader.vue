<script>
export default {
  name: 'Header',
};
</script>

<template>
  <header class="bg-primary text-white">
    <div class="container d-flex justify-content-between py-2">
      <div>Logo</div>
      <nav>
        <ul class="list-unstyled m-0 p-0 gap-4 d-flex">
          <li>
            <router-link
              :to="{ name: 'home' }"
              class="text-white text-decoration-none"
              >Home</router-link
            >
          </li>
          <li>
            <router-link
              :to="{ name: 'projects' }"
              class="text-white text-decoration-none"
              >Projects</router-link
            >
          </li>
          <li>
            <router-link
              :to="{ name: 'about' }"
              class="text-white text-decoration-none"
              >About</router-link
            >
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<style scoped lang="scss"></style>
