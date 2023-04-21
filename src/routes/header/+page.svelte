<script>
    import { animateScroll } from "svelte-scrollto-element";
    import { onMount } from "svelte";

    /**
     * @type {number}
     */
    let scrollOffset;

    onMount(() => {
        let viewHeight = window.innerHeight;
        scrollOffset = (viewHeight / 10) * -1;
    });
    // This function is made to dynammically calculate and pass in the users
    // screen height and set the scroll-to-element offset.
    function returnScrollOffset() {
        return scrollOffset;
    }
</script>

<header class="header sticky">
    <div class="header__wrapper">
        <a
            href="/"
            class="header__intro"
            on:click={() => animateScroll.scrollToTop()}
        >
            <svg
                width="38"
                height="39"
                viewBox="0 0 38 39"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
            >
                <rect
                    x="3"
                    y="5"
                    width="31"
                    height="29"
                    stroke="#33363F"
                    stroke-width="2"
                />
                <path
                    d="M10 15L14 19.5L10 24"
                    stroke="#33363F"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                />
                <path
                    d="M19 24H27"
                    stroke="#33363F"
                    stroke-width="2"
                    stroke-linecap="round"
                />
            </svg>
            <span>Alvis Franks</span>
        </a>

        <ul class="header__navigation">
            <li>
                <!-- svelte-ignore a11y-click-events-have-key-events -->
                <!-- svelte-ignore a11y-missing-attribute -->
                <a
                    href="#skills"
                    on:click={() =>
                        animateScroll.scrollTo({
                            element: "#skills",
                            offset: returnScrollOffset(),
                        })}>Skills</a
                >
            </li>
            <li>
                <!-- svelte-ignore a11y-click-events-have-key-events -->
                <!-- svelte-ignore a11y-missing-attribute -->
                <a
                    href="#portfolio"
                    on:click={() =>
                        animateScroll.scrollTo({
                            element: "#portfolio",
                            offset: returnScrollOffset(),
                        })}>Projects</a
                >
            </li>
            <li>
                <!-- svelte-ignore a11y-click-events-have-key-events -->
                <!-- svelte-ignore a11y-missing-attribute -->
                <a
                    href="#contactme"
                    on:click={() =>
                        animateScroll.scrollTo({
                            element: "#contactme",
                            offset: returnScrollOffset(),
                        })}>Contact me</a
                >
            </li>
        </ul>
    </div>
</header>

<style lang="scss">
    $rich-black: #040f0f;

    .header {
        @import "src/global-colors.scss";
        display: flex;
        justify-content: center;
        // border-bottom: solid 2px $rich-black;
        position: relative;
        z-index: 5;
        background-color: $platinum;

        &__wrapper {
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: 100%;
            max-width: 1400px;
            padding: 0 2rem;
            height: 10vh;
        }
        &__intro {
            display: flex;
            flex-direction: row;
            align-items: center;
            svg {
                padding-right: 0.5rem;
            }
        }
    }
    :global(.sticky) {
        position: fixed !important;
        top: 0;
        width: 100%;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }
    span {
        font-size: 2.3rem;
    }
    ul {
        display: flex;
        flex-direction: row;
        gap: 2rem;
        list-style-type: none;
        padding: 0;
    }
</style>
