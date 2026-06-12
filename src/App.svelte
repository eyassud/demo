<script>
  import Funny from "./Funny.svelte";
  import MissionPossible from "./MissionPossible.svelte";

  let fontSize = 150;
  let color = "green";
</script>

<h1>Font Size: {fontSize}</h1>
<MissionPossible color={color} />
<Funny {fontSize} />
