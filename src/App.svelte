<script>
  import Navbar from "./Navbar.svelte";
  import Player from "./Player.svelte";

  let players = [
    {
      name: "John Doe",
      points: 53
    },
    {
      name: "Sam Smith",
      points: 45
    },
    {
      name: "Sara Wilson",
      points: 34
    }
  ];
</script>

<Navbar />
<div class="container">
  {#each players as { name, points }}
    <Player {name} {points} />
  {:else}
    <p>No Players</p>
  {/each}
</div>
