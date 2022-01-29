<template>
  <div>
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
const posts = [
  {
    title: 'Forese',
    description: 'FORESE is a student-run forum and an extension of the Placement cell.',
    link: 'https://www.forese.co.in/',
    image: 'https://www.forese.co.in/assets/images/logo/logo.png',
    time: 1643389348857
  },
  {
    title: 'Rotaract Club of SVCE',
    description: 'Rotaract clubs bring together people ages 18 and older to exchange ideas with leaders in the community, develop leadership and professional skills, and have fun through service.',
    link: 'https://www.rotary.org/',
    image: 'https://www.rotary.org/sites/all/themes/rotary_rotaryorg/images/rotary-logo-color-2019-simplified.svg',
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