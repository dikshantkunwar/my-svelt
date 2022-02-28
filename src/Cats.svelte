<script>
  let cats = [
    { id: 'J---aiyznGQ', name: 'Keyboard Cat' },
		{ id: 'z_AbfPXTKms', name: 'Maru' },
		{ id: 'OUtn3pvWmpg', name: 'Henri The Existential Cat' }
  ];
</script>

<div>
  <h1>The Famous Cats of Internet</h1>
  <ul>
    {#each cats as cat}
      <li><a target="_blank" href="https://www.youtube.com/watch?v={cat.id}">
        {cat.name}
      </a></li>
    {/each}
  </ul>
</div>