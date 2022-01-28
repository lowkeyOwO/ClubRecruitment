<template>
  <div>
<NuxtLink to = "/post" class = "fixed bg-blue-400 hover:bg-blue-500 transition duration-500 ease-in-out top-0 right-0 p-4 w-12 h-12 font-bold text-center flex flex-col items-center justify-center"><span>+</span></NuxtLink>
    <div v-for="item in posts" :key="item.title" class="p-4">
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
const posts = [
  {
    title: 'never gonna give you up',
    content: 'never gonna give you up',
    link: 'https://www.youtube.com/watch?v=dQw4w9WgXcQ',
    image: 'https://i.insider.com/61135525ad63f30019501966?width=700',
    time: 1643389348857
  },
  {
    title: '111',
    content: '111',
    link: '111',
    image: '111',
    time: 1643389341529
  }
]
export default {
  async asyncData() {
    return {
      posts: posts.sort((a, b) => a.time - b.time).reverse(),
    }
  },
}
</script>