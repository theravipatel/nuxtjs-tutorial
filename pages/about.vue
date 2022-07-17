<template>
  <div>
    <Header></Header>
    <h1>About Page</h1>
  </div>
</template>

<script>
export default {
  name: 'AboutPage',
  head() {
    return {
      title: 'About | Nuxt-Js Tutorial',
      meta: [
        {
          title: 'About | Nuxt-Js Tutorial',
          name: 'description',
          content: 'About | Nuxt-Js Tutorial'
        },
        {
          hid: 'description',
          name: 'description',
          content: 'About page description | Nuxt-Js Tutorial'
        },
        {
          hid: 'og:title',
          name: 'og:title',
          content: 'About | Nuxt-Js Tutorial'
        },
        {
          hid: 'og:description',
          name: 'og:description',
          content: 'About page description | Nuxt-Js Tutorial'
        }
      ]
    }
  }
}
</script>
