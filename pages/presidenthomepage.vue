<template>
  <div>
<NuxtLink to = "/post" class = "fixed bg-blue-400 hover:bg-blue-500 transition duration-500 ease-in-out top-0 right-0 p-4 w-12 h-12 font-bold text-center flex flex-col items-center justify-center"><span>+</span></NuxtLink>
    <div v-for="item in posts" :key="item.title" class="p-10">
      <CollectionCard
        :title="item.title"
        :description="item.description"
        :image="item.image"
        :link="item.link"
      />
    </div>
  </div>
</template>
<script>
export default {
  async asyncData() {
    return {
      posts: posts.sort((a, b) => a.time - b.time).reverse(),
    }
  },
}
</script>