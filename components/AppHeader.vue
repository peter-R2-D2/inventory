<template>
  <!-- Sidebar -->
  <div
    :class="[
      isOpen ? 'w-64' : 'w-16',
      'h-screen bg-gray-800 text-white transition-all duration-300',
    ]"
  >
    <div class="flex items-center justify-between px-4 py-4">
      <span v-if="isOpen" class="text-xl font-semibold">Menu</span>
      <button @click="toggleMenu">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
          stroke-width="2"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M4 6h16M4 12h16m-7 6h7"
          />
        </svg>
      </button>
    </div>

    <!-- Navigation Links -->
    <ul class="mt-4">
      <li v-for="item in menuItems" :key="item.id" class="px-4 py-2">
        <NuxtLink
          :to="{ name: item.route }"
          class="flex items-center space-x-4 hover:bg-gray-700 rounded-lg p-2"
        >
          <Icon :name="item.icon" />
          <span v-if="isOpen">{{ item.name }}</span>
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script setup>
const isOpen = ref(true);
const menuItems = [
  {
    id: 1,
    name: "Dashboard",
    icon: "material-symbols:space-dashboard",
    route: "dashboard",
  },
  {
    id: 2,
    name: "Inventario",
    icon: "material-symbols:inventory",
    route: "inventory",
  },
  {
    id: 3,
    name: "Configuración",
    icon: "material-symbols:settings",
    route: "settings",
  },
  { id: 4, name: "POS", icon: "material-symbols:point-of-sale", route: "pos" },
];
const toggleMenu = () => {
  isOpen.value = !isOpen.value;
};
</script>

<style scoped>
/* Add any additional custom styles if necessary */
</style>
