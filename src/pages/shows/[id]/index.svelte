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
  <article>
    <img
      src={show.image.medium}
      alt="cover"
      style="float: left; margin-right: 2em;" />
    <h1>{show.name}</h1>
    <p>
      {@html show.summary}
    </p>
  </article>
{/if}
