<template>
  <div>
    <h1>Layout 2 Page</h1>
  </div>
</template>

<script>
export default {
  name: 'Layout2Page',
  layout: 'Layout2',
  head() {
    return {
      title: 'Layout2 | Nuxt-Js Tutorial | '+ process.env.SITE_NAME,
      meta: [
        {
          title: 'Layout2 | Nuxt-Js Tutorial',
          name: 'description',
          content: 'Layout2 | Nuxt-Js Tutorial'
        },
        {
          hid: 'description',
          name: 'description',
          content: 'Layout2 page description | Nuxt-Js Tutorial'
        },
        {
          hid: 'og:title',
          name: 'og:title',
          content: 'Layout2 | Nuxt-Js Tutorial'
        },
        {
          hid: 'og:description',
          name: 'og:description',
          content: 'Layout2 page description | Nuxt-Js Tutorial'
        }
      ]
    }
  }
}
</script>
