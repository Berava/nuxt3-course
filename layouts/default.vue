<template>
  <div class="flex h-full">
    <!-- START : SIDEBAR -->
    <div></div>
    <!-- END : SIDEBAR -->
    <div
      class="fixed top-0 bottom-0 left-0 w-64 py-5 bg-primary text-primary-content"
    >
      <h1 class="mt-5 text-2xl font-bold px-5">DT Merch</h1>
      <ul class="menu w-full mt-10 px-0">
        <li
          v-for="menuItem in menuItems"
          :class="menuItem.path === $route.path ? 'bordered' : 'hover-bordered'"
        >
          <nuxt-link :to="menuItem.path">{{ menuItem.title }}</nuxt-link>
        </li>
      </ul>
    </div>

    <!-- START : MAIN CONTENT -->
    <div class="w-full pl-64">
      <div :class="$route.path === '/' ? '' : 'p-5'">
        <slot />
      </div>
    </div>
    <!-- END : PAGE -->
  </div>
</template>

<script setup>
const menuItems = [
  { path: "/", title: "Accueil" },
  { path: "/category/head", title: "Tête" },
  { path: "/category/body", title: "Hauts" },
  { path: "/category/other", title: "Autres" },
];
</script>

<style scoped>
.menu li.hover-bordered a:hover,
.menu li.bordered a {
  @apply border-primary-content;
}
</style>
