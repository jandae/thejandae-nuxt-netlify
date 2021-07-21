<template>
  <main>
    <section class="self-center flex flex-col items-center justify-center">
      <img id="logo" src="~/assets/img/thejandae.svg" alt="thejandae" />
    </section>

    <section class="mt-8">
      <h3 class="text-primary-600 dark:text-primary-400 max-w-5xl mx-auto">Latest blog post</h3>
      <posts post-type="blog" :amount="1" />
    </section>
  </main>
</template> 
<style scoped>
#logo {
  width: 80%;
}
</style>