<script>
  import Header from "../components/Header.svelte";
  import Footer from "../components/Footer.svelte";
  import { getDatabase, ref, push } from "firebase/database";

  let title;
  let description;
  let wordList = Array(10).fill("");

  async function writeGameData() {
    const db = getDatabase();
    push(ref(db, "items/"), {
      title: title,
      description: description,
      wordList: wordList,
    });
  }

  const moveToPlay = () => {
    window.location.hash = "#/play";
  };
</script>

<Header />

<button on:click={() => console.log(title, description, wordList)}
  >테스트</button
>
<form on:submit|preventDefault={writeGameData}>
  <div>
    <div><label for="title">Title</label></div>
    <input
      type="text"
      id="title"
      name="title"
      placeholder="제목을 입력하세요."
      required
      bind:value={title}
    />
  </div>
  <description>
    <div><label for="description">Description</label></div>
    <input
      type="text"
      id="description"
      name="description"
      placeholder="간단한 설명을 입력하세요."
      required
      bind:value={description}
    />
  </description>
  <wordlist>
    <div><label for="word-list">Word List</label></div>
    {#each wordList as word, index}
      <input
        type="text"
        id="word-list-{index}"
        name="word-list-{index}"
        placeholder={`Word ${index + 1}`}
        required
        bind:value={wordList[index]}
      />
    {/each}
  </wordlist>
  <div>
    <button class="submit-btn" on:click={moveToPlay}>Submit</button>
  </div>
</form>

<Footer />

<style>
  .submit-btn {
    width: 200px;
    background-color: #fcb83b;
    margin-top: 10px;
    cursor: pointer;
    color: black;
    padding: 5px 12px;
  }
</style>
