<script lang="ts" context="module">

</script>

<script lang="ts">
  import SEO from "svelte-seo";
  import Home from "$lib/pages/Home.svelte";
  import Work from "$lib/pages/Work.svelte";
  import Projects from "$lib/pages/Projects.svelte";
  //import Events from "$lib/pages/Events.svelte";
  import Skills from "$lib/pages/Skills.svelte";
  import About from "$lib/pages/About.svelte";
  import Footer from "$lib/pages/Footer.svelte";

/* basic colors at  https://tailwindcss.com/docs/customizing-colors   more at  https://hypercolor.dev/   */ 
  let primaryBackground = "bg-zinc-900 dark:bg-zinc-900";
  let neutralBackground = "bg-zinc-900 dark:bg-zinc-900";
</script>

<SEO
  title="Angel Santoyo"
  description="portfolio site"
  canonical="https://angelsantoyo.com"
/>

<Home />

<Work backgroundClass={neutralBackground} />
<!-- <Projects backgroundClass={primaryBackground}  /> -->
<!-- <Skills backgroundClass={primaryBackground} /> -->
<!-- <Events backgroundClass={neutralBackground} /> -->
<About backgroundClass={neutralBackground} />

<Footer  />