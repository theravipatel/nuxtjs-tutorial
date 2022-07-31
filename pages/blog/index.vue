<template>
  <div>
    <h1>Blog Page</h1>
    <ol>
      <li>
        <nuxt-link to="/blog/1">Blog Title 1</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/blog/2">Blog Title 2</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/blog/3">Blog Title 3</nuxt-link>
      </li>
    </ol>
  </div>
</template>

<script>
export default {
  name: 'BlogPage',
  head() {
    return {
      title: 'Blog | Nuxt-Js Tutorial | '+ process.env.SITE_NAME,
      meta: [
        {
          title: 'Blog | Nuxt-Js Tutorial',
          name: 'description',
          content: 'Blog | Nuxt-Js Tutorial'
        },
        {
          hid: 'description',
          name: 'description',
          content: 'Blog page description | Nuxt-Js Tutorial'
        },
        {
          hid: 'og:title',
          name: 'og:title',
          content: 'Blog | Nuxt-Js Tutorial'
        },
        {
          hid: 'og:description',
          name: 'og:description',
          content: 'Blog page description | Nuxt-Js Tutorial'
        }
      ]
    }
  }
}
</script>
