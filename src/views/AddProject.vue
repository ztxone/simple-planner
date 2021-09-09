<template>
  <form
    @submit.prevent="handleSubmit"
    class="mt-10 flex flex-col items-center bg-white rounded-2xl p-8"
  >
    <label
      class="flex self-start text-gray-400 my-6 text-xs uppercase font-bold"
      >Заголовок:</label
    >
    <input
      type="text"
      v-model="title"
      required
      class="block p-2 w-full text-gray-300 focus:text-gray-500 box-border border-b border-gray-400  mb-4"
    />
    <label
      class="flex self-start text-gray-400 my-6 text-xs uppercase font-bold"
      >Описание:</label
    >
    <textarea
      v-model="details"
      required
      class="block h-40 p-2 w-full text-gray-300 focus:text-gray-500 box-border border-b border-gray-400  mb-4"
    ></textarea>
    <button
      class="mt-6 bg-green-400 text-white font-semibold py-3 px-5 rounded-2xl"
    >
      Добавить проект
    </button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      title: "",
      details: "",
    }
  },
  methods: {
    handleSubmit() {
      let project = {
        title: this.title,
        details: this.details,
        complete: false,
      }

      fetch("http://localhost:3000/projects", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify(project),
      })
        .then(() => {
          this.$router.push("/")
        })
        .catch((err) => console.log(err))
    },
  },
}
</script>

<style></style>
