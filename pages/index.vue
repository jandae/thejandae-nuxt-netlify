<template>
  <main>
    <section class="self-center flex flex-col items-center justify-center">
      <img id="logo" src="~/assets/img/thejandae.svg" alt="thejandae" />
    </section>

    <socials></socials>

    <section class="mt-8 mx-auto">
      <h3 class="text-primary-600 dark:text-primary-400 max-w-5xl mx-auto">Latest posts</h3>
      <posts post-type="links" :amount="20" />
    </section>
  </main>
</template> 
<style scoped>
#logo {
  width: 80%;
}
</style>
