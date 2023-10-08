<script lang="ts">
  import Glow from '$lib/components/special/glow.svelte'
  import Button from '$lib/components/shared/button.svelte'
  import { onMount } from 'svelte'
  import Typewriter from 'svelte-typewriter'
  import { fade } from 'svelte/transition'
  import Card from '$lib/components/shared/card.svelte'

  let hasEntered = false
  let audio: HTMLAudioElement

  const play = () => {
    audio = new Audio('/assets/her.mp3')
    audio.loop = true
    audio.play()
    hasEntered = true
  }
  onMount(() => () => audio.pause())

  let showGlow = false
</script>

{#if !hasEntered}
  <div
    class="absolute inset-0 flex items-center justify-center bg-black z-10"
    out:fade={{ duration: 888 }}
  >
    <div
      role="group"
      on:mouseenter={() => (showGlow = true)}
      on:mouseleave={() => (showGlow = false)}
      class="flex items-center justify-center p-32"
    >
      <button
        on:click={play}
        class="text-white hover:scale-105 transition-transform"
      >
        Enter the Portal
      </button>
    </div>
    <Glow {showGlow} />
  </div>
{:else}
  <img
    class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 z-[-1]"
    src="/assets/metame.png"
    alt="Meta Me"
  />
  <Glow />
  <div
    class="typer page mx-auto h-full flex flex-col gap-6 md:gap-10 items-center justify-center"
  >
    <Typewriter mode="loop" interval={120}>
      <h2>Master...</h2>
      <h2>SvelteKit</h2>
      <h2>SupaBase</h2>
      <h2>LiveKit</h2>
      <h2>Tailwind</h2>
      <h2>TypeScript</h2>
      <h2>All-in-one Kit</h2>
      <h2>Welcome to...</h2>
      <h2>Miss Litt Kittt</h2>
    </Typewriter>
    <Card let:C>
      <C.Header>BrightSide Developer's Latest Creation!</C.Header>
      <C.Body
        ><p class="text-center">
          Miss Litt Kittt is the Ultimate Tech Stack to Develop High Quality
          Social Applications at Rapid Speeds.
        </p>
      </C.Body>
    </Card>
    <div class="hover:scale-105 transition-transform">
      <Button
        className="!rounded-full"
        variant="glass"
        size="xl"
        href="/?sign-up">Join Now!</Button
      >
    </div>
  </div>
{/if}

<!-- ZS5V0PjibePMhjNP -->
<style lang="postcss">
  .typer {
    --cursor-color: #d41876;
    --cursor-width: 3px;
  }
  h2 {
    @apply text-[45px] md:text-[72px] font-bold;
    background: -webkit-linear-gradient(45deg, #ebb305, #d41876);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    padding-bottom: 1rem;
  }
</style>
