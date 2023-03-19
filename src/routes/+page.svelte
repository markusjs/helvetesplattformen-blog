<script>
  import ArrowRightIcon from '$lib/components/ArrowRightIcon.svelte'
  import PostsList from '$lib/components/PostsList.svelte'
  import { author, intro , title } from '$lib/info.js'

  /** @type {import('./$types').PageData} */
  export let data
</script>

<svelte:head>
  <title>{title}</title>
  <meta name="description" content={intro} />
</svelte:head>

<div class="flex flex-col flex-grow gap-8 pb-16">
  <!-- bio -->
  <section class="flex flex-col items-center gap-16 pt-8 pb-16">
    <div class="flex flex-col w-full gap-6 rounded-lg">
<!--       <img
        src={avatar}
        alt={name}
        class="mx-auto rounded-full w-36 h-36 ring-2 ring-zinc-200 dark:ring-zinc-700"
      /> -->
      <p class="text-base text-zinc-600 dark:text-zinc-400">
        <b>{intro}</b>
        <br>
        {author}
      </p>
    </div>
  </section>
  <section class="w-full">
    <div class="flex items-center justify-between gap-4 mb-8">
      <h2 class="text-sm font-medium sm:text-base text-zinc-500 dark:text-zinc-400">
        Siste nyhetssaker
      </h2>
      <a href="/posts" class="flex items-center gap-1 text-sm font-medium text-teal-500"
        >Se alle <ArrowRightIcon class="w-4 h-4" /></a>
    </div>
    <PostsList posts={data.posts} />
  </section>
</div>
