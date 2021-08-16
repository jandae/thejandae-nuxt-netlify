<template>
  <main>
    <section class="self-center flex flex-col items-center justify-center">
      <img id="logo" src="~/assets/img/thejandae.svg" alt="thejandae" />
    </section>

    <div class="inline-grid grid-cols-2 gap-4 mt-8">
      <a
        class="btn px-1 items-center justify-center"
        href="https://www.youtube.com/channel/UCS4bNn83QPhGftBoGmKf7ew"
        target="_blank"
        >Tech Youtube</a
      >
      <a
        class="btn px-1 items-center justify-center"
        href="https://www.youtube.com/channel/UCOmgOC5nvjRiobtlFnoyZKQ"
        target="_blank"
        >DIY Youtube</a
      >
      <a
        class="btn px-1 items-center justify-center"
        href="https://www.tiktok.com/@thejandae?lang=en&is_copy_url=1&is_from_webapp=v1"
        target="_blank"
        >Tiktok</a
      >
      <a class="btn px-1 items-center justify-center" href="https://www.twitch.tv/thejandae" target="_blank">Twitch</a>
      <a class="btn px-1 items-center justify-center" href="https://www.twitch.tv/thebedgaming" target="_blank"
        >Gaming Twitch</a
      >
      <a class="btn px-1 items-center justify-center" href="https://www.facebook.com/thejandae.page" target="_blank"
        >Facebook</a
      >

      <a
        class="btn px-1 items-center justify-center"
        href="https://www.facebook.com/gaming/thebedgaming"
        target="_blank"
        >Facebook Gaming</a
      >

      <a class="btn px-1 items-center justify-center" href="https://github.com/jandae" target="_blank"
        >Github (Warning! Janky)</a
      >
    </div>

    <section class="mt-8">
      <h3 class="text-primary-600 dark:text-primary-400 max-w-5xl mx-auto">Latest posts</h3>
      <posts post-type="links" :amount="10" />
    </section>
  </main>
</template> 
<style scoped>
#logo {
  width: 80%;
}
</style>
