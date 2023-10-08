<header>
  <slot name="lead" />
  <slot name="trail" />
</header>

<style lang="postcss">
  header {
    @apply flex items-center justify-between sticky top-0 z-10;
    @apply px-6;
    @apply w-full h-[var(--header-height)];
    @apply bg-accent/25 shadow-md backdrop-blur;
  }
</style>
