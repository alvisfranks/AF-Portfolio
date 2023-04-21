<script>
    import Hero from "./hero/+page.svelte";
    import Skills from "./skills/+page.svelte";
    import Title from "./title-block/+page.svelte";
    import Projects from "./project/+page.svelte";
    import Contact from "./contact/+page.svelte";
</script>

<svelte:head>
    <title>Alvis Franks portfolio, Svelte version.</title>
</svelte:head>

<Hero />
<Title titleText="I work with" navAnchor="skills" />
<Skills />
<Title titleText="Projects I have worked on" navAnchor="portfolio" />
<Projects />
<Title titleText="Need a web developer?" navAnchor="contactme" />
<Contact />
