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
    class="typer page mx-auto h-full flex flex-col md:flex-row gap-6 items-center justify-center md:justify-around"
  >
    <div class="mx-auto flex flex-col gap-10 md:w-[32rem] md:m-0">
      <div class="w-fit mx-auto">
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
      </div>
      <div class="hidden md:flex mx-auto flex-col">
        <ul>
          <li class="text-lg">
            Uses <span class="font-bold">SvelteKit</span> as app
            <span class="underline">frame-work</span>.
          </li>
          <li class="text-lg">
            <span class="font-bold">SupaBase</span> for
            <span class="underline">authentication</span>
            and <span class="underline">database</span>.
          </li>
          <li class="text-lg">
            <span class="font-bold">LiveKit</span> for realtime
            <span class="underline">text</span>,
            <span class="underline">audio</span> and
            <span class="underline">video</span> communication.
          </li>
          <li class="text-lg">
            <span class="font-bold">Tailwind</span> for
            <span class="underline">styling</span>.
          </li>
          <li class="text-lg">
            And <span class="font-bold">TypeScript</span> for
            <span class="underline">type-safety</span>.
          </li>
        </ul>
      </div>
    </div>

    <div class="flex flex-col gap-6 md:gap-10 items-center justify-center">
      <Card className="max-w-[25rem]" let:C>
        <C.Header>BrightSide Developer's Latest Creation!</C.Header>
        <C.Body
          ><p class="text-center">
            Miss Litt Kittt is the Ultimate Tech Stack to Develop High Quality
            Social Applications at Rapid Speeds.
          </p>
        </C.Body>
      </Card>
      <Button
        className="!rounded-full"
        variant="glass"
        size="xl"
        href="/?sign-up">Join Now!</Button
      >
    </div>
    <div class="text-center flex md:hidden mx-auto flex-col">
      <ul>
        <li class="text-lg">
          Uses <span class="font-bold">SvelteKit</span> as app
          <span class="underline">frame-work</span>.
        </li>
        <li class="text-lg">
          <span class="font-bold">SupaBase</span> for
          <span class="underline">authentication</span>
          and <span class="underline">database</span>.
        </li>
        <li class="text-lg">
          <span class="font-bold">LiveKit</span> for realtime
          <span class="underline">text</span>,
          <span class="underline">audio</span> and
          <span class="underline">video</span> communication.
        </li>
        <li class="text-lg">
          <span class="font-bold">Tailwind</span> for
          <span class="underline">styling</span>.
        </li>
        <li class="text-lg">
          And <span class="font-bold">TypeScript</span> for
          <span class="underline">type-safety</span>.
        </li>
      </ul>
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
