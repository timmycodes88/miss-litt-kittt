<script>
  import CardBody from './card/card-body.svelte'
  import CardFooter from './card/card-footer.svelte'
  import CardHeader from './card/card-header.svelte'

  let C = {
    Header: CardHeader,
    Body: CardBody,
    Footer: CardFooter,
  }
</script>

<div>
  <slot {C} />
</div>

<style lang="postcss">
  div {
    @apply relative flex flex-col gap-3 p-6 rounded-lg border-primary/80 bg-primary/30 border;
  }
</style>
