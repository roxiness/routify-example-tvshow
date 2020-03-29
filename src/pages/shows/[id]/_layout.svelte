<script>
  import { params } from "@sveltech/routify";
  $: id = $params.id;
  let show;

  async function fetchShow(id) {
    const response = await fetch(`https://api.tvmaze.com/shows/${id}`);
    show = await response.json();
  }

  $: if (id) fetchShow(id);
</script>

{#if show}
<div>
    <a href="/shows/{id}">
    Main
    </a>
    <a href="/shows/{id}/details">Details</a>
  <slot scoped={{ show }}>Loading...</slot>
</div>
{/if}
