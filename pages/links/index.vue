<template>
  <main>
    <div class="w-full max-w-5xl mx-auto text-center">
      <div class="mb-8">
        <p>Yo Welcome!</p>
        <p>Scroll down for the links.</p>
        <br />
        <p class="animate-bounce">&darr;</p>
        <br />
        <p>
          consider
          <br />
          <strong>subscribing</strong>
          <br />
          <br />
          <strong>:)</strong>
        </p>
      </div>
      <socials class="mb-8" />
    </div>

    <section v-if="posts" class="w-full max-w-5xl mx-auto">
      <h1 class="title text-center">Links</h1>
      <posts post-type="links" :amount="100" />
    </section>
    <socials />
  </main>
</template>

<script>
export default {
  async asyncData({ $content, error }) {
    let posts
    try {
      posts = await $content('links').fetch()
    } catch (e) {
      error({ message: 'Blog posts not found' })
    }
    return { posts }
  },
}
</script>
