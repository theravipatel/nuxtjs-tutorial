<template>
  <div>
    <h1>Layout 1 Page</h1>
  </div>
</template>

<script>
export default {
  name: 'Layout1Page',
  layout: 'Layout1',
  head() {
    return {
      title: 'Layout1 | Nuxt-Js Tutorial | '+ process.env.SITE_NAME,
      meta: [
        {
          title: 'Layout1 | Nuxt-Js Tutorial',
          name: 'description',
          content: 'Layout1 | Nuxt-Js Tutorial'
        },
        {
          hid: 'description',
          name: 'description',
          content: 'Layout1 page description | Nuxt-Js Tutorial'
        },
        {
          hid: 'og:title',
          name: 'og:title',
          content: 'Layout1 | Nuxt-Js Tutorial'
        },
        {
          hid: 'og:description',
          name: 'og:description',
          content: 'Layout1 page description | Nuxt-Js Tutorial'
        }
      ]
    }
  }
}
</script>
