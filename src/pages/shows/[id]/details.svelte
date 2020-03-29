<script>
  export let scoped;
  $: show = scoped.show;
  const keys = ["language", "runtime", "status", 'url', 'officialSite'];
</script>

<article>
  <h1>{show.name}</h1>
  
  <table>
    {#each keys as key}
      <tr>
        <td><b>{key}</b></td>
        <td>{show[key]}</td>
      </tr>
    {/each}
  </table>
</article>
