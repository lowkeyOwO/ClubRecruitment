<template>
  <div>
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
export default {
  async asyncData() {
    const postx = await fetch('http://localhost:3001/posts')
const posts = await postx.json()
    console.log(posts)
    return {
      posts: posts.sort((a, b) => a.time - b.time).reverse(),
    }
  },
}
</script>