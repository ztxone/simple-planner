<template>
  <nav class="flex justify-evenly items-center my-6">
    <router-link
      :to="{ name: 'Home' }"
      class="flex text-xl p-2 pt-3 rounded-md cursor-pointer"
    >
      <span class="mr-2"
        ><svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"
          /></svg
      ></span>
      Проекты
    </router-link>
    <router-link
      :to="{ name: 'AddProject' }"
      class="flex text-xl p-2 pt-3 rounded-md cursor-pointer"
    >
      <span class="mr-2"
        ><svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M12 9v3m0 0v3m0-3h3m-3 0H9m12 0a9 9 0 11-18 0 9 9 0 0118 0z"
          /></svg
      ></span>
      Добавить новую запись
    </router-link>
  </nav>
</template>

<script>
export default {}
</script>

<style>
a.router-link-active {
  border-bottom: 2px solid limegreen;
  background-color: white;
}
</style>
