<script>
  import Header from '$lib/components/layout/header.svelte'
  import Button from '$lib/components/shared/button.svelte'
</script>

<Header>
  <h1 slot="lead">Miss Litt Kittt</h1>
  <Button
    className="!rounded-full"
    variant="secondary"
    slot="trail"
    href="/?login"
  >
    <span class="md:hidden">Join</span>
    <span class="hidden md:inline">Create an Account</span>
  </Button>
</Header>

<slot />
