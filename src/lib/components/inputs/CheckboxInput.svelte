<script lang="ts">
  import { Switch } from '@rgossiaux/svelte-headlessui';

  export let checked = false;
</script>

<Switch
  bind:checked
  on:click={(e) => e.stopPropagation()}
  on:change
  class="relative inline-flex h-7 w-7 items-center rounded-full {checked
    ? 'bg-sky-600 dark:bg-purple-900'
    : 'border border-stone-400 bg-white dark:bg-slate-200'}"
>
  <span
    class="absolute m-[-1px] h-[1px] w-[1px] overflow-hidden whitespace-nowrap border-0 p-0"
    style="clip: rect(0, 0, 0, 0)"
  />
  <span
    class="inline-block h-5 w-5 translate-x-1 rounded-full bg-gradient-to-tr from-sky-400 to-purple-400 ring-2 ring-white transition-all dark:ring-slate-300"
    class:opacity-100={checked}
    class:opacity-0={!checked}
  />
</Switch>
