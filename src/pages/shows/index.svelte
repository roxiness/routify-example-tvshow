<script>
  const shows = [
    [32, "Fargo (2014)"],
    [179, "The Wire (2002)"],
    [318, "Community (2009)"],
    [5, "True Detective (2014)"],
    [532, "Scrubs (2001)"],
    [30960, "Cobra Kai (2018)"],
    [530, "Seinfeld (1989)"],
    [347, "It's Always Sunny in Philadelphia (2005)"]
  ];
</script>

<header>
  <h3>My recommended shows to watch this month are</h3>
  <a href="/shows/suggest">Suggest a show</a>
</header>

<section>
  {#each shows as [id, name]}
    <aside>
      <a href="/shows/{id}">{name}</a>
    </aside>
  {/each}
</section>
