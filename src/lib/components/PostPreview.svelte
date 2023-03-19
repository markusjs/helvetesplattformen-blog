<script>
  import Card from './Card.svelte'
  import ArrowRightIcon from './ArrowRightIcon.svelte'

  export let post
</script>

<Card href={`/post/${post.slug}`} data-sveltekit-prefetch>
  <slot slot="eyebrow" name="eyebrow" />
  <slot slot="title">{post.title}</slot>
  <div slot="description" class="prose dark:prose-invert">
    {@html post.preview.html}
  </div>
</Card>

<style>
  .prose > :global(p) {
    margin-top: 0;
    margin-bottom: 0;
  }
</style>
