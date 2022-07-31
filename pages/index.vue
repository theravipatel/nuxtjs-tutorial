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
      title: 'Home | Nuxt-Js Tutorial | '+ process.env.SITE_NAME,
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
  },
  mounted() {
    console.log("App Environment is : ",process.env.APP_ENV);
  }
}
</script>
