<script>
  import "../app.css";
  import Navbar from "$lib/header.svelte";
  import Footer from "$lib/footer.svelte";
  import Slider from "$lib/slider.svelte";
</script>

<header>
  <Navbar />
  <Slider />
</header>

<main>
  <slot />
</main>

<footer>
  <Footer />
</footer>
