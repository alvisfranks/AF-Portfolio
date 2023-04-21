<script>
    /**
     * @type {string}
     */
    export let titleText;
    /**
     * @type {string}
     */
    export let navAnchor;
</script>

<div class="title-wrapper" id={navAnchor}>
    <h2>{titleText}</h2>
</div>

<style lang="scss">
    @import "src/global-colors.scss";

    .title-wrapper {
        background-color: $rich-black;
        display: flex;
        justify-content: center;
    }

    h2 {
        font-size: 3rem;
        color: $platinum;
        text-align: center;
        padding: 2rem 0;
        border-bottom: solid 1px $platinum;
        width: 100%;
        max-width: 1400px;
    }
</style>
