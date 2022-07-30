<template>
  <div>
    <h1>Home Page</h1>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  head() {
    return {
      title: 'Home | Nuxt-Js Tutorial',
      meta: [
        {
          title: 'Home | Nuxt-Js Tutorial',
          name: 'description',
          content: 'Home | Nuxt-Js Tutorial'
        },
        {
          hid: 'description',
          name: 'description',
          content: 'Home page description | Nuxt-Js Tutorial'
        },
        {
          hid: 'og:title',
          name: 'og:title',
          content: 'Home | Nuxt-Js Tutorial'
        },
        {
          hid: 'og:description',
          name: 'og:description',
          content: 'Home page description | Nuxt-Js Tutorial'
        }
      ]
    }
  }
}
</script>
