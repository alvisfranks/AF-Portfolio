<section class="hero">
  <div class="wrapper-img">
    <img src="assets/af-cutout-v3-small.png" alt="alvis profile pic" />
  </div>
  <div class="wrapper-text">
    <div class="description">
      <h1>Hi! It's Alvis!</h1>
      <p>
        Web developer from Latvia, 28 years old, with a background in creative
        digital content production. Adept at turning ideas into final products
        and solving problems. Experienced in web development and coding, with a
        fondness for minimalist and elegant aesthetics. Technologically
        knowledgeable, constantly reading and researching new tech and AI tools.
        Strong communication skills and a calm, respectful demeanor even in
        conflict situations.
      </p>
    </div>
  </div>
</section>

<style lang="scss">
  .hero {
    height: 90vh;
    background-color: rgb(43, 43, 43);
    color: #fff;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 0;
    position: relative;

    .wrapper-img {
      width: 100%;
      height: 100%;
      max-width: 1400px;
      display: flex;
      // max-height: 100%;
      justify-content: flex-start;
      align-items: flex-end;
      // height: 100%;
      vertical-align: bottom;

      img {
        filter: saturate(0);
        // height: 100%;
        // margin-right: 30%;
        height: 100%;
        z-index: 0;
        // overflow: hidden;
      }
    }

    .wrapper-text {
      position: absolute;
      width: 100%;
      max-width: 1400px;
      display: flex;
      justify-content: flex-end;

      .description {
        max-width: 700px;
        z-index: 2;
        h1 {
          font-size: 5rem;
          font-weight: 300;
        }
        p {
          font-size: 1.5rem;
          line-height: 1.5;
        }
      }
    }
  }
</style>
