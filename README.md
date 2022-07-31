# Nuxt Js Tutorial
## A) Ref. - Nuxt Intro - https://www.smashingmagazine.com/2020/04/getting-started-nuxt/
## B) Ref. - Nuxt Directories - https://nuxtjs.org/docs/directory-structure/

## 1) Create app
```
npm init nuxt-app nuxt-demo
```

## 2) Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

## 3) Routing 
- Create new page in 'pages' directory and run url with pagename i.e. http://localhost:3000/about
- When new page created, route automatically define in '.nuxt\router.js' so no need to manually define route like vuejs
- In 'components' directory, we can define common layout i.e. header.vue which we use in any pages by just adding component's name as a tag i.e. <Header />. No need to write 'import header from...' 

## 4) Dynamic Routing 
- For dynamic routing, we can create sub folder in 'pages' directory i.e. 'pages/blog' and in that directory, create new index.vue file for listing purpose and for dynamic routing, create new file with '_pagename.vue' i.e. '/pages/blog/_id.vue'
- In mounted() method, we can get url parameters by using this.$route

```
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
  }
}
</script>
```


## 5) Head Method, Title, Seo meta title & description
- To change title, meta data; use head() method
```
<template>
  <div>
    <Header></Header>
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
```

## Default Layout
- Create 'app.html' file in root directory which will work as default index page of the app. Note app.html file should be same as '.nuxt\views\app.template.html' in terms of attributes.
- Create 'layouts' folder in root and add 'default.vue' file for setting defult layout of the app. Note: make sure to add "<Nuxt />" tag in the layout file so pages content will load there. 
```
<template>
    <div>
       <Header></Header>
       <Nuxt /> 
    </div>
</template>
```

## Multiple Layout
- Create Multiple layout files as per requirement in layout folder and set it as page's layout as per below. By default 'default.vue' is set as layout.
```
<script>
export default {
  name: 'NewPage',
  layout: 'Layout1',
}
</script>
```

## Error Page
- Create 'error.vue' in layout folder which will work as default error page. Define error layout in same layout folder to change design if required.
- layouts/error.vue
```
<template>
<div>
    <h1>Page Not Found</h1>
    <h5>Error: {{ error }}</h5>
</div>
</template>
<script>
export default {
  name: 'ErrorPage',
  layout: 'ErrorLayout',
  props: {
    error: {
        type: Object,
        default: null,
    }
  }
}
</script>

```

- layouts/ErrorLayout.vue
```
<template>
<div>
    <Header></Header>
    <Nuxt />
</div>
</template>
```

## Middleware
- Ref. : (https://nuxtjs.org/docs/directory-structure/middleware/)
- The middleware directory contains your application middleware. Middleware lets you define custom functions that can be run before rendering either a page or a group of pages (layout).
- Three type of middleware: Router Middleware, Named Middleware, Anonymous Middleware


## Router Middleware
- This will be act as global middleware apply to all router and can be define as below.
- middleware/router_middleware.js
```
export default function ({ route }) { //export default function (context) {
  console.log("Router Middleware called");
}
```

- Then, in your nuxt.config.js, use the router.middleware key.
```
router: {
  middleware: 'router_middleware'
}
```

## Named Middleware 
- This will be apply to only in page where it added by its name.
- middleware/named_middleware.js
```
export default function ({ store, redirect }) { //export default function (context) {
  console.log("Named Middleware called");
}
```

- Then, in your vue page,
- pages/NewPage.vue
```
<template>
  <h1>New Page</h1>
</template>

<script>
  export default {
    middleware: 'named_middleware'
  }
</script>
```

## Anonymous Middleware
- This can be define as a function in the page where it is required. So no need to create JS file for it in Middleware file.
- pages/NewPage.vue
```
<template>
  <h1>New Page</h1>
</template>

<script>
  export default {
    middleware({ store, redirect }) {
      console.log("Anonymous Middleware called");
    }
  }
</script>
```

## Module
- 
## .env Module
- Install dotenv module
```
npm i @nuxtjs/dotenv
```

- To add dotenv module in nuxt.config.js, 

- Mehtod 1) Add '@nuxtjs/dotenv' in nuxt.config.js file in modules array and restart app
```
modules: [
  '@nuxtjs/axios',
  '@nuxtjs/dotenv'
]
```

- Mehtod 2) Add '@nuxtjs/dotenv' in nuxt.config.js file in modules array with default filename and restart app
```
modules: [
  '@nuxtjs/axios',
  ['@nuxtjs/dotenv', { filename: '.env.prod' }]
]
```

- Create .env file in root and add variables
```
SECRETE_KEY=ABCD123
SITE_URL=https://www.google.com/
```

- In any page, use it as below
```
export default {
  mounted() {
    console.log(".env file:",process.env.SECRETE_KEY);
  }
}
```



## Documentation

For detailed explanation on how things work, check out the [documentation](https://nuxtjs.org).

## Special Directories

You can create the following extra directories, some of which have special behaviors. Only `pages` is required; you can delete them if you don't want to use their functionality.

### `assets`

The assets directory contains your uncompiled assets such as Stylus or Sass files, images, or fonts.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/assets).

### `components`

The components directory contains your Vue.js components. Components make up the different parts of your page and can be reused and imported into your pages, layouts and even other components.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/components).

### `layouts`

Layouts are a great help when you want to change the look and feel of your Nuxt app, whether you want to include a sidebar or have distinct layouts for mobile and desktop.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/layouts).


### `pages`

This directory contains your application views and routes. Nuxt will read all the `*.vue` files inside this directory and setup Vue Router automatically.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/get-started/routing).

### `plugins`

The plugins directory contains JavaScript plugins that you want to run before instantiating the root Vue.js Application. This is the place to add Vue plugins and to inject functions or constants. Every time you need to use `Vue.use()`, you should create a file in `plugins/` and add its path to plugins in `nuxt.config.js`.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/plugins).

### `static`

This directory contains your static files. Each file inside this directory is mapped to `/`.

Example: `/static/robots.txt` is mapped as `/robots.txt`.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/static).

### `store`

This directory contains your Vuex store files. Creating a file in this directory automatically activates Vuex.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/store).
