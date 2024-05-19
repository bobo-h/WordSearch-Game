<script>
  import Header from "../components/Header.svelte";
  import Footer from "../components/Footer.svelte";

  const moveToMaking = () => {
    window.location.hash = "#/making";
  };
</script>

<Header />
<main>
  <div class="main-board">
    <div class="main-board__img">게임화면</div>
    <div class="main-board__dsc">게임설명</div>
  </div>
  <div>
    <button class="making-btn" on:click={moveToMaking}>게임만들기</button>
  </div>
</main>
<Footer />

<style>
  .making-btn {
    cursor: pointer;
  }
</style>
