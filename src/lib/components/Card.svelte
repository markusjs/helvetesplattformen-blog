<script>
  export let as = 'div'
  export let href = undefined

  let _class = undefined
  export { _class as class }
</script>

<svelte:element this={as} class={['relative flex flex-col items-start group', _class].join(' ')}>
  <slot name="eyebrow" />

  {#if $$slots.title}
    <div class="text-base font-semibold tracking-tight text-zinc-800 dark:text-zinc-100">
        <div>
          <slot name="title" />
        </div>
    </div>
  {/if}

  {#if $$slots.description}
    <div
      class="relative z-10 flex-1 text-sm text-zinc-600 dark:text-zinc-400"
      class:mt-2={!!$$slots.title}
    >
      <slot name="description" />
    </div>
  {/if}

  {#if $$slots.actions}
    <div aria-hidden="true" class="relative z-10 flex items-center mt-4">
      <slot name="actions" />
    </div>
  {/if}
</svelte:element>
