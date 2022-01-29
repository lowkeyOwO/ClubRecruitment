<template>
  <div
    class="
      mx-auto
      max-w-4xl
      rounded-2xl
      bg-white
      p-4
      md:flex
      flex-row
      space-x-2
      items-center 
    "
  >
    <div class="p-2">
      <img :src="image" :alt="title" class="w-48 h-48" />
    </div>
    <div class="p-2 flex flex-col space-y-4">
      <div class="text-content">
        <span class="text-4xl font-bold">
          {{ title }}
        </span>
      </div>
      <div class="description">
        <h3>
          {{ description }}
        </h3>
      </div>
      <a
        :href="link"
        class="
          rounded-lg
          p-2 w-36 text-center
          bg-gray-700
          hover:bg-gray-600
          transform text-white
          hover:translate-y-1
          transition
          duration-500
          ease-in-out
        "
        >Apply Now</a
      >
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: null,
    },
    description: {
      type: String,
      default: null,
    },
    link: {
      type: String,
      default: null,
    },
    image: {
      type: String,
      default: null,
    },
  },
}
</script>

