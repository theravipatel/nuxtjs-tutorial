<template>
  <div>
    <h1>About Page</h1>
  </div>
</template>

<script>
export default {
  name: 'AboutPage',
  middleware: ['named_middleware'],
  head() {
    return {
      title: 'About | Nuxt-Js Tutorial | '+ process.env.SITE_NAME,
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
