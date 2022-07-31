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
