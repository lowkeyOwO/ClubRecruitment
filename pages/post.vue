<template>
  <div
    class="
      bg-white
      rounded-lg
      max-w-3xl
      mx-auto
      hover:max-w-4xl
      p-4
      flex flex-col
      items-center
      justify-start
      space-y-4
    "
  >
    <div class="py-2 text-black font-bold text-4xl">CREATE POST</div>
    <input
      type="text"
      v-model="title"
      name=""
      placeholder="Title"
      class="w-72 border-black border-2 rounded-xl p-4 h-12 text-center"
    />
    <div class="wrapper">
      <textarea
        placeholder="Content"
        v-model="content"
        class="w-72 border-black border-2 rounded-xl p-4 resize-y text-center"
      ></textarea>
    </div>
    <input
      type="link"
      v-model="link"
      name=""
      placeholder="Forms Link"
      class="w-72 border-black border-2 rounded-xl p-4 h-12 text-center"
    />
    <input
      type="link"
      v-model="image"
      name=""
      placeholder="Image Link"
      class="w-72 border-black border-2 rounded-xl p-4 h-12 text-center"
    />
    <button
      class="
        bg-gray-700
        p-3
        rounded-md
        text-white
        w-36
        transition
        duration-500
        ease-in-out
        hover:bg-gray-600
      "
      @click="createPost"
    >
      Login
    </button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: '',
      content: '',
      link: '',
      image: '',
    }
  },
  methods: {
    createPost() {
      if (!this.title || !this.content || !this.link || !this.image)
        return this.$toast.global.missing()
      return this.$toast.global.success()
    },
  },
}
</script>