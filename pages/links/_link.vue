<template>
  <main>
    <section v-if="post">
      <nav class="mb-8" aria-label="go back">
        <router-back class="block" />
      </nav>

      <article>
        <!-- <h5
          v-if="post.createdAt"
          class="inline-block py-1 px-2 my-2 bg-gray text-white text-sm font-medium rounded-sm whitespace-no-wrap"
        >
          {{ formatDate(post.createdAt) }}
        </h5> -->
        <h1 class="">{{ post.description }}</h1>
        <p class="mt-1 mb-4 text-primary-600 dark:text-primary-400">{{ post.title }}</p>
        <nuxt-content :document="post" class="article-content" />
      </article>
    </section>
  </main>
</template>

<script>
export default {
  async asyncData({ $content, params, error }) {
    let post
    try {
      post = await $content('links', params.link).fetch()
    } catch (e) {
      error({ message: 'Link post not found' })
    }
    return { post }
  },
  methods: {
    formatDate(dateString) {
      const date = new Date(dateString)
      return date.toLocaleDateString(process.env.lang) || ''
    },
  },
}
</script>

<style  lang="scss">
.article-content {
  a:after {
    content: url("data:image/svg+xml;charset=UTF-8, <svg aria-hidden= 'true' focusable= 'false' data-prefix= 'fas' data-icon= 'external-link-square-alt' class='svg-inline--fa fa-external-link-square-alt fa-w-14' role= 'img' xmlns= 'http://www.w3.org/2000/svg' viewBox='0 0 448 512' ><path fill= 'white' d='M448 80v352c0 26.51-21.49 48-48 48H48c-26.51 0-48-21.49-48-48V80c0-26.51 21.49-48 48-48h352c26.51 0 48 21.49 48 48zm-88 16H248.029c-21.313 0-32.08 25.861-16.971 40.971l31.984 31.987L67.515 364.485c-4.686 4.686-4.686 12.284 0 16.971l31.029 31.029c4.687 4.686 12.285 4.686 16.971 0l195.526-195.526 31.988 31.991C358.058 263.977 384 253.425 384 231.979V120c0-13.255-10.745-24-24-24z'></path></svg>");
    width: 15px;
    height: 17px;
    display: inline-block;
    margin-left: 5px;
    opacity: 0.3;
  }

  h2 {
    a:after {
      content: '';
    }
  }
}
</style>
