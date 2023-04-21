<script>
    // @ts-nocheck

    import { onMount, tick } from "svelte";
    let projects = [
        {
            title: "Livland homepage",
            picture: [
                "assets/livland/livland-web.webp",
                "assets/livland/livland-mobile.webp",
            ],
            stackTop: [
                "Wordpress CMS",
                "Custom Design",
                "ACF Extended",
                "SCSS",
            ],
            stackBottom: ["SwiperJS", "Responsive", "Multilang"],
            anchorLink: "https://www.livland.lv",
        },
        {
            title: "I un M serviss webshop",
            picture: [
                "assets/iunm/iunm-desktop-700x455px.webp",
                "assets/iunm/iunm-mobile-screen.webp",
            ],
            stackTop: [
                "Wordpress",
                "Elementor",
                "Slider Revolution",
                "E-commerce",
            ],
            stackBottom: ["Video headers", "Responsive", "API integration"],
            anchorLink: "https://www.iunmserviss.lv",
        },
        {
            title: "E6 webshop",
            picture: ["assets/e6/web.webp", "assets/e6/mobile.webp"],
            stackTop: ["Wordpress", "Elementor", "Slider Revolution"],
            stackBottom: [
                "Woocommerce",
                "Video headers",
                "ChatGPT",
                "Midjourney",
            ],
            anchorLink: "https://www.e6.lv",
        },
    ];
    /**
     * @type {HTMLUListElement[]}
     */
    let loadedProjects = [];
    /**
     * @type {HTMLUListElement[]}
     */
    let loadedSection = [];

    onMount(() => {
        // After all project blocks has loaded in the DOM, this loop
        // counts the number of projects and executes the addSpacers()
        // function as many times as project count and every time giving the
        // index argument.
        let projectCount = loadedProjects.length;
        for (let t = 0; t < projectCount; t++) {
            addSpacers(t);
            addDividers(t);
        }
    });

    /**
     * @param {number} index
     */
    function addSpacers(index) {
        let containerChildren = Array.from(loadedProjects[index].childNodes);

        for (let i = 0; i < containerChildren.length - 1; i++) {
            if (containerChildren[i].nodeType !== 1) {
                continue;
            }
            const spacer = document.createElement("div");
            spacer.classList.add("list-spacer");

            const img = document.createElement("img");
            img.src = "assets/splitter-line.svg";
            spacer.appendChild(img);

            loadedProjects[index].insertBefore(
                spacer,
                containerChildren[i + 1]
            );
        }
    }
    /**
     * @param {number} index
     */
    function addDividers(index) {
        const container = loadedSection[index];
        const isLastContainer = index === loadedSection.length - 1;

        if (!isLastContainer) {
            const divider = document.createElement("div");
            divider.classList.add("project-divider");

            const line = document.createElement("div");
            line.className = "white-line";
            divider.appendChild(line);

            container.appendChild(divider);
        }
    }
</script>

{#each projects as projectData, index}
    <section class="project" bind:this={loadedSection[index]}>
        <div class="project-wrapper">
            <h3 class="headline">{projectData.title}</h3>
            <a href={projectData.anchorLink}>
                <div class="devices-wrapper">
                    <div class="pc-wrapper">
                        <div class="devices-pc">
                            <img
                                src="assets/screen-frame-macbook.svg"
                                alt="macbook screen"
                                class="svg-holder-pc"
                            />
                            <div class="project-pic-desktop">
                                <img
                                    src={projectData.picture[0]}
                                    alt="project-pic-desktop"
                                />
                            </div>
                        </div>
                    </div>
                    <div class="phone-wrapper">
                        <div class="devices-phone">
                            <img
                                src="assets/phone-frame-iphone.svg"
                                alt="iphone screen"
                                class="svg-holder-mobile"
                            />
                            <img
                                src={projectData.picture[1]}
                                alt="project-pic-mobile"
                                class="project-pic-mobile"
                            />
                        </div>
                    </div>
                </div>
            </a>
            <div class="techstack-row-1">
                <ul bind:this={loadedProjects[index]}>
                    {#each projectData.stackTop as item}
                        <li>{item}</li>
                    {/each}
                </ul>
            </div>
            <div class="techstack-row-2">
                <ul>
                    {#each projectData.stackBottom as item}
                        <li>{item}</li>
                    {/each}
                </ul>
            </div>
        </div>
    </section>
{/each}

<style lang="scss">
    @import "src/global-colors.scss";

    .headline {
        text-align: center;
        font-weight: 600;
        text-transform: uppercase;
        color: $platinum;
        font-size: 26px;
        padding: 2rem 0;
        margin: 0;
    }
    .project {
        background-color: $rich-black;
    }

    .devices-wrapper {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
    }
    .pc-wrapper {
        display: flex;
        justify-content: center;
    }
    .devices-pc {
        position: relative;
        max-width: 700px;
        display: inline-flex;
        justify-content: center;
        align-items: flex-start;
        margin-top: -25px;

        .svg-holder-pc {
            position: absolute;
            z-index: 2;
            width: 104%;
        }
        .project-pic-desktop {
            width: 100%;
            display: flex;
            justify-content: center;
            img {
                aspect-ratio: 16/10;
                width: 100%;
                border-radius: 2%;
                object-fit: cover;
                object-position: top;
            }
        }
    }
    .phone-wrapper {
        display: flex;
        justify-content: center;
        z-index: 2;
    }
    .devices-phone {
        position: relative;
        max-width: 250px;
        display: flex;
        justify-content: center;
        align-items: center;

        .project-pic-mobile {
            width: 100%;
            height: 100%;
            border-radius: 2vmin;
            object-fit: cover;
            object-position: top;
        }

        .svg-holder-mobile {
            width: 103%;
            position: absolute;
        }
    }

    ul {
        display: flex;
        flex-direction: row;
        gap: 2rem;
        padding: 0;
        li {
            color: $platinum;
            list-style-type: none;
            font-size: 25px;
        }
    }

    .techstack-row-1 {
        display: flex;
        justify-content: center;
        font-weight: 500;
    }
    .techstack-row-2 {
        display: flex;
        justify-content: center;
        ul {
            display: flex;
            gap: 50px;
            li {
                font-size: 16px;
                font-weight: 200;
                text-align: center;
            }
        }
    }
    :global(.project-divider) {
        height: 5rem;
        display: flex;
        justify-content: center;
        padding: 3rem 0;
    }
    :global(.white-line) {
        background-color: $platinum;
        height: 100%;
        width: 1px;
    }
</style>
