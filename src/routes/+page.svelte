<script>
    import Header from '../components/Header.svelte';
    import Footer from '../components/Footer.svelte';
    import CharacterList from '../components/CharacterList.svelte';
  </script>
  
  <Header />
  
  <main>
    <CharacterList />
  </main>
  
  <Footer />
  
  <style>
    main { padding: 0 1rem; }
  </style>