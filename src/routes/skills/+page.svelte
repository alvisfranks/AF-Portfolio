<section class="skills" id="skills">
    <div class="skills__wrapper">
        <div class="pair-wrapper">
            <div class="web-development">
                <span>Web Development</span>
                <div class="line" />
                <ul class="skill-items">
                    <li>Figma</li>
                    <li>Wordpress CMS</li>
                    <li>SvelteKit Framework</li>
                    <li>Slider Revolution</li>
                    <li>HTML, SCSS, JS</li>
                    <li>High sense of responibility</li>
                </ul>
            </div>
            <div class="content-creation">
                <span>Content creation</span>
                <div class="line" />
                <ul class="skill-items">
                    <li>Adobe Premiere Pro</li>
                    <li>Adobe Photoshop</li>
                    <li>Adobe Illustrator</li>
                    <li>Adobe Lightroom</li>
                    <li>Notebook and Pen (ideas)</li>
                </ul>
            </div>
            <div class="new-tech">
                <span>New tech I play with</span>
                <div class="line" />
                <ul class="skill-items">
                    <li>ChatGPT</li>
                    <li>DALL-E 2</li>
                    <li>Midjourney</li>
                    <li>Stable Diffusion</li>
                </ul>
            </div>
        </div>
    </div>
</section>

<style lang="scss">
    $rich-black: #040f0f;
    $platinum: #e5e7e6;
    .skills {
        background-color: $rich-black;
        color: $platinum;
        display: flex;
        justify-content: center;
        padding-bottom: 3rem;
        z-index: 5;
        &__wrapper {
            width: 100%;
            max-width: 1400px;
        }
        .web-development,
        .content-creation,
        .new-tech {
            display: flex;
            flex-direction: row;
            justify-content: center;
            align-items: center;
            gap: 20px;
            span {
                border: solid 1px $platinum;
                padding: 1rem;
                width: 100%;
                max-width: 250px;
                text-align: center;
                font-size: 1.6rem;
            }
        }
        ul {
            text-align: end;
            list-style-type: none;
            border: 1px solid $platinum;
            padding: 1.4rem;
            width: 100%;
            max-width: 350px;
        }
        .line {
            width: 100%;
            max-width: 100px;
            background-color: $platinum;
            height: 1px;
        }
        li {
            font-size: 1.6rem;
        }
        .pair-wrapper {
            padding-top: 1rem;
        }
    }
</style>
