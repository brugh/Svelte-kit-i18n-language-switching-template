<script lang="typescript">
  import Header from "../components/UI/Header.svelte";
  import Footer from "../components/UI/Footer.svelte";
  import CharacterList from "../components/CharacterList.svelte";
  import { initLang } from '../components/UI/Locale.svelte';
  initLang();
</script>

<Header />

<main>
  <CharacterList />
</main>

<Footer />

<style>
  main {
    margin: 1rem;
    padding: 0 1rem;
  }
</style>
