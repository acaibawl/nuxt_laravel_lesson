<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title red">
        {{ greet }} // デフォルトの「nuxt」から変更した
      </h1>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          rel="noopener noreferrer"
          class="button--green"
        >
          Documentation
        </a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          rel="noopener noreferrer"
          class="button--grey"
        >
          GitHub
        </a>
      </div>
    </div>
  </div>
</template>

<script>
import Vue from 'vue'

export default Vue.extend({
  async asyncData ({ app }) {
    const greet = await app.$axios.$get('/').catch(err => console.log(err))
    return { greet }
  }
})
</script>
