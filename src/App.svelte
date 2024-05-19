<script>
  import Login from "./pages/Login.svelte";
  import Main from "./pages/Main.svelte";
  import Making from "./pages/Making.svelte";
  import Notfound from "./pages/Notfound.svelte";
  import Play from "./pages/Play.svelte";
  import Signup from "./pages/Signup.svelte";
  import Router from "svelte-spa-router";
  import "./css/style.css";

  const routes = {
    "/": Main,
    "/login": Login,
    "/making": Making,
    "/play": Play,
    "/signup": Signup,
    "*": Notfound,
  };
</script>

<Router {routes} />
