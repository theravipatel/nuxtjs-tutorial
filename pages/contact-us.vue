<template>
  <div>
    <h1>Contact Us Page</h1>
  </div>
</template>

<script>
export default {
  name: 'ContactUsPage',
  middleware({ store, redirect }) {
    console.log("Anonymous Middleware called");
  },
  head() {
    return {
      title: 'Contact Us | Nuxt-Js Tutorial | '+ process.env.SITE_NAME,
      meta: [
        {
          title: 'Contact Us | Nuxt-Js Tutorial',
          name: 'description',
          content: 'Contact Us | Nuxt-Js Tutorial'
        },
        {
          hid: 'description',
          name: 'description',
          content: 'Contact Us page description | Nuxt-Js Tutorial'
        },
        {
          hid: 'og:title',
          name: 'og:title',
          content: 'Contact Us | Nuxt-Js Tutorial'
        },
        {
          hid: 'og:description',
          name: 'og:description',
          content: 'Contact Us page description | Nuxt-Js Tutorial'
        }
      ]
    }
  }
}
</script>
