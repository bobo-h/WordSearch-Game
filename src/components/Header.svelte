<script>
  const moveToSignup = () => {
    window.location.hash = "#/signup";
  };

  const moveToLogin = () => {
    window.location.hash = "#/login";
  };
</script>

<header>
  <a class="info-logo" href="/"><div>Word Search Game</div></a>
  <div class="info-btn">
    <button class="info-btn__signup" on:click={moveToSignup}>Sign up</button>
    <button class="info-btn__login" on:click={moveToLogin}>Login</button>
  </div>
</header>

<style>
  header {
    margin-top: 60px;
    border-bottom: 1px solid #d1d1d1;
    padding-bottom: 20px;
  }

  .info-logo {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .info-logo div {
    margin-top: 25px;
    font-size: 50px;
    font-weight: bold;
    position: absolute;
    color: black;
  }
  .info-btn {
    display: flex;
    justify-content: flex-end;
    align-items: flex-end;
    right: 10px;
  }

  .info-btn__signup {
    text-decoration: none;
    background-color: #fffeb9;
    color: black;
    padding: 10px;
    border-radius: 20px;
  }

  .info-btn__login {
    margin-left: 10px;
    text-decoration: none;
    background-color: #fffeb9;
    color: black;
    padding: 10px;
    border-radius: 20px;
  }
</style>
