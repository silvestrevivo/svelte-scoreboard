<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  let player = {
    name: "",
    points: 0
  };

  const onSubmit = e => {
    e.preventDefault();
    dispatch("addplayer", player);
    // here we reset the player object, no setState() needed like in React
    player = {
      name: "",
      points: 0
    };
  };
</script>

<form class="grid-3" on:submit={onSubmit}>
  <input type="text" placeholder="Player Name" bind:value={player.name} />
  <input type="text" placeholder="Player Points" bind:value={player.points} />
  <input type="submit" class="btn btn-primary" value="Add Player" />
</form>
