<script>
    import Header from "../routes/header/+page.svelte";
    import Footer from "../routes/footer/+page.svelte";
    import "../global-styles.scss";
</script>

<Header />
<div class="header-spacer" />
<slot />
<Footer />

<style>
    .header-spacer {
        height: 10vh;
    }
</style>
