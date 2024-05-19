<script>
  import Header from "../components/Header.svelte";
  import Footer from "../components/Footer.svelte";
  import { getDatabase, ref, onValue } from "firebase/database";
  import { onMount } from "svelte";

  let items = [];

  const db = getDatabase();
  const itemsRef = ref(db, "items/");

  onMount(() => {
    onValue(itemsRef, (snapshot) => {
      const data = snapshot.val();
      items = data ? Object.values(data) : [];
    });
  });
</script>

<Header />
<main>
  <h1>Game Data</h1>
  {#if items.length > 0}
    <ul>
      {#each items as item}
        <li>
          <h2>{item.title}</h2>
          <p>{item.description}</p>
          <ul>
            {#each item.wordList as word}
              <li>{word}</li>
            {/each}
          </ul>
        </li>
      {/each}
    </ul>
  {:else}
    <p>No games found.</p>
  {/if}
</main>
<Footer />

<style>
</style>
