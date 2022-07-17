<template>
  <div>
    <Header></Header>
    <h1>Blog Detail Page</h1>
    <h5><b>Blog Id: {{ id }}</b></h5>
  </div>
</template>

<script>
export default {
  name: 'BlogDetailPage',
  data() {
    return {
      id: ''
    }
  },
  mounted() {
    console.log(this.$route);
    this.id = this.$route.params.id;
  },
  head() {
    return {
      title: 'Blog Title '+ this.id +' | Nuxt-Js Tutorial',
      meta: [
        {
          title: 'Blog Title '+ this.id +' | Nuxt-Js Tutorial',
          name: 'description',
          content: 'Home | Nuxt-Js Tutorial'
        },
        {
          hid: 'description',
          name: 'description',
          content: 'Blog Title '+ this.id +' page description | Nuxt-Js Tutorial'
        },
        {
          hid: 'og:title',
          name: 'og:title',
          content: 'Blog Title '+ this.id +' | Nuxt-Js Tutorial'
        },
        {
          hid: 'og:description',
          name: 'og:description',
          content: 'Blog Title '+ this.id +' page description | Nuxt-Js Tutorial'
        }
      ]
    }
  }
}
</script>
