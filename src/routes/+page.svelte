<script lang="ts" context="module">

</script>

<script lang="ts">
  import SEO from "svelte-seo";
  import Skills from "$lib/pages/Skills.svelte";
  import Work from "$lib/pages/Work.svelte";
  import About from "$lib/pages/About.svelte";
  import Home from "$lib/pages/Home.svelte";
  import Projects from "$lib/pages/Projects.svelte";
  import Footer from "$lib/pages/Footer.svelte";

/* basic colors at  https://tailwindcss.com/docs/customizing-colors   more at  https://hypercolor.dev/   */ 
  let primaryBackground = "bg-gradient-to-r from-slate-900 to-blue-900";
  let neutralBackground = "bg-neutral-200 dark:bg-neutral-900";
</script>

<SEO
  title="Angel Santoyo"
  description="portfolio site"
  canonical="https://angelsantoyo.com"
/>

<Home />

<Work backgroundClass={neutralBackground} />
<Projects backgroundClass={primaryBackground}  />
<Skills backgroundClass={neutralBackground} />
<About backgroundClass={primaryBackground} />
<Footer  />