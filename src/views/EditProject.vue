<template>
  <h1 class="text-lg text-center">Редактировать запись:</h1>
  <form
    @submit.prevent="updateProject"
    class="mt-4 flex flex-col items-center bg-white rounded-2xl p-8"
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
      Сохранить изменения
    </button>
  </form>
</template>

<script>
export default {
  props: ["id"],
  data() {
    return {
      title: "",
      details: "",
      uri: "http://localhost:3000/projects/" + this.id,
    }
  },
  mounted() {
    fetch(this.uri)
      .then((res) => res.json())
      .then((data) => {
        this.title = data.title
        this.details = data.details
      })
      .catch((err) => console.log(err))
  },
  methods: {
    updateProject() {
      fetch(this.uri, {
        method: "PATCH",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          title: this.title,
          details: this.details,
        }),
      })
        .then(() => {
          this.$router.push("/")
        })
        .catch((err) => console.log(err.message))
    },
  },
}
</script>

<style></style>
