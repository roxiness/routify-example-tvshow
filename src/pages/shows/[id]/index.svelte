<script>
  export let scoped;
  $: show = scoped.show;
</script>

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
