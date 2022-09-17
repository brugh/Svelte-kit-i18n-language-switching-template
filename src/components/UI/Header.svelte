<script lang="ts">
  import Locale from "./Locale.svelte";
  import { _ } from "svelte-i18n";
</script>

<header class="hero">
  <div class="hero-body">
    <div class="contiainer">
      <h1 class="title">{$_("app.title")}</h1>
      <h2 class="subtitle">{$_("app.slogan")}</h2>
      <Locale />
    </div>
  </div>
</header>
