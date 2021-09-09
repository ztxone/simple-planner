<template>
  <nav class="flex items-center">
    <button
      @click="updateFilter('all')"
      :class="{ 'bg-gray-200': current === 'all' }"
      class="px-2 py-1 mr-3 shadow rounded-md text-xs uppercase hover:bg-gray-200"
    >
      Все
    </button>
    <button
      @click="updateFilter('ongoing')"
      :class="{ 'bg-gray-200': current === 'ongoing' }"
      class="px-2 py-1 mr-3 shadow rounded-md text-xs uppercase hover:bg-gray-200"
    >
      Активные
    </button>
    <button
      @click="updateFilter('completed')"
      :class="{ 'bg-gray-200': current === 'completed' }"
      class="px-2 py-1 mr-3 shadow rounded-md text-xs uppercase hover:bg-gray-200"
    >
      Выполненные
    </button>
  </nav>
</template>

<script>
export default {
  props: ["current"],
  methods: {
    updateFilter(by) {
      this.$emit("filterChange", by)
    },
  },
}
</script>

<style></style>
