<script>
  import { url, isActive } from "@sveltech/routify";
  import { params } from "@sveltech/routify";
  $: id = $params.id;

  const links = [
    ["./index", "MAIN"], 
    ["./details", "DETAILS"]
  ];
  let show;

  async function fetchShow(id) {
    const response = await fetch(`https://api.tvmaze.com/shows/${id}`);
    show = await response.json();
  }

  $: if (id) fetchShow(id);
</script>

<style>
  a {
    padding: 2px 6px 3px;
  }
  a.active {
    background: var(--color-secondary);
    color: white;
  }
</style>

{#if show}
  {#each links as [path, name]}
    <a href={$url(path)} class:active={$isActive(path)}>{name}</a>
  {/each}
  <slot scoped={{ show }}>Loading...</slot>
{/if}
