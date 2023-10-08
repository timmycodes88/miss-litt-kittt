<script lang="ts">
  import { cn } from '$lib/utils'

  export let href: string | undefined
  export let disabled: boolean = false
  export let variant:
    | 'default'
    | 'secondary'
    | 'outline'
    | 'ghost'
    | 'link'
    | 'glass' = 'default'
  export let size: 'sm' | 'xl' | 'icon' | '' = ''
  export let className: string = ''
</script>

{#if !!href}
  <a
    class={cn(
      variant,
      size,
      disabled && 'pointer-events-none opacity-50',
      className
    )}
    {href}
  >
    <slot />
  </a>
{:else}
  <button
    class={cn(variant, size, disabled && 'opacity-50', className)}
    {disabled}
  >
    <slot />
  </button>
{/if}

<style lang="postcss">
  /* Base */
  a,
  button {
    @apply inline-flex justify-center items-center rounded-md font-medium transition-all px-4 py-2;
    @apply hover:scale-[1.01] hover:shadow-md hover:brightness-[0.9];
  }

  /* Sizes */
  .xl {
    @apply py-4 min-w-[12rem] text-xl font-semibold;
  }

  /* Variants */
  .default {
    @apply bg-primary text-primary-foreground;
  }
  .secondary {
    @apply bg-accent text-accent-foreground;
  }
  .glass {
    @apply bg-primary/70 backdrop-blur text-primary-foreground hover:shadow-none;
  }
</style>
