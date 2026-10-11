<!-- jenny note: remember to add: aria-label, aria-describedby -->
<svelte:head>
  <title>it's jennymade</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link
    href="https://fonts.googleapis.com/css2?family=Atkinson+Hyperlegible:ital,wght@0,400;0,700;1,400;1,700&family=Instrument+Serif:ital@0;1&family=Libre+Caslon+Condensed:ital,wght@0,400..700;1,400..700&family=Readex+Pro:wght@160..700&display=swap"
    rel="stylesheet"
  />
</svelte:head>
<div class="portfolioWrapper" role="region">
  <div class="portfolioHeaderSection">
    <h1 class="portfolioHeader">
      <p class="defineJenny">
        jennymade <span class="wordType">adjective</span>
      </p>
      <p class="definition">
        making data, research and <i>human</i> stories
        <b>accessible</b>
        and <b>visually impactful</b>
      </p>
      <!-- <p>
        <span class="portfolioHedKicker"
          >messy data + concepts of a plan &#8594; accesssible, visually
          impactful storytelling</span
        >
        <br />
        it's <span class="jenny">jenny</span>made
      </p>
      <p class="portfolioSubHed">
        making data, research and <i>human</i> stories <br />accessible and
        visually impactful
      </p> -->
    </h1>
  </div>
  <div class="scrollIndicatorContainer">
    <p class="scrollInstructions">scroll for past work</p>
    <div aria-hidden="true" class="scrollIndicator"></div>
  </div>
  <div class="scrollWrapper__run">
    <div class="portfolioStage">
      <div class="cardContainer">
        <div class="cardGroup">
          <h2 class="cardCategory">🎨 ui/ux design</h2>
          <div class="card first">Item 1</div>
          <div class="card second">Item 2</div>
          <div class="card third">Item 3</div>
          <div class="card fourth">Item 4</div>
        </div>
        <div class="cardGroup">
          <h2 class="cardCategory">📊 data viz</h2>
          <div class="card first">
            <img
              class="cardImg"
              src="src/lib/assets/hero-images/cra-pt1.png"
              alt="TKTK"
            />
          </div>
          <div class="card second">Item 2</div>
          <div class="card third">Item 3</div>
        </div>
        <div class="cardGroup">
          <h2 class="cardCategory">🖌️ illustration</h2>
          <div class="card first">Item 1</div>
          <div class="card second">Item 2</div>
          <div class="card third">Item 3</div>
        </div>
        <div class="cardGroup">
          <h2 class="cardCategory">research</h2>
          <div class="card first">
            <img
              class="cardImg"
              src="src/lib/assets/hero-images/airbnb-chart-screenshot.png"
              alt="Chart showing top four neighborhoods for Airbnb as of January 2026"
            />
          </div>
          <div class="card second">Item 2</div>
          <div class="card third">Item 3</div>
        </div>
      </div>
    </div>
  </div>
</div>

<style>
  :root {
    /* put imported fonts */
    /* @import url("https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&display=swap"); */
    --cardWidth: 250px;
    --cardHeight: 350px;
    font-family: "Libre Caslon Condensed", serif;
    font-weight: 400;
    font-style: normal;
  }

  .portfolioWrapper {
    height: 100vh;
    overflow-y: auto;
    background-color: rgba(56, 102, 65, 0.75); /* solitaire green */
    border-radius: 10px;
  }

  .scrollIndicatorContainer {
    margin-top: 5rem;
  }

  .scrollIndicator {
    width: 1px;
    height: 5rem;
    margin: 0 auto;
    background: #fff;
    transform: scaleY(0);
    transform-origin: top center;
    animation: scrolldown 3s ease-in-out infinite;
  }

  @keyframes scrolldown {
    0% {
      transform: scaleY(0);
    }
    70% {
      transform: scaleY(1);
    }
    100% {
      transform: scaleY(1);
    }
  }

  @media (prefers-reduced-motion: reduce) {
    .scrollIndicator {
      animation: none;
      transform: scaleY(1);
    }
  }

  .scrollInstructions {
    margin-bottom: 1rem;
    text-align: center;
    color: #fff;
    font-size: 1rem;
  }

  .portfolioHeader {
    color: #fff;
    font-size: 3rem;
    font-weight: 700;
    text-align: center;
    margin: 0 auto;
    max-width: 425px;

    .wordType {
      font-size: 1.5rem;
      font-weight: 500;
      font-style: normal;
      opacity: 0.75;
    }

    .definition {
      margin-top: -2rem;
      font-size: 1.5rem;
      font-weight: 400;
      font-style: normal;
    }

    .portfolioHedKicker {
      font-weight: 500;
      font-size: 2.5rem;
    }

    .jenny {
      font-family: "Libre Caslon Condensed", serif;
      font-size: 3rem;
      letter-spacing: 0.15rem;
      font-style: italic;
      vertical-align: baseline;
    }

    /* not using right now */
    /* span {
      font-size: 1rem;
      vertical-align: middle;
    } */

    .portfolioSubHed {
      font-weight: 300;
      font-size: 1.25rem;
      margin-top: -2rem;
      /* letter-spacing: -0.05rem; */
      /* font-style: italic; */
    }
  }

  .scrollWrapper__run {
    height: 250vh;
  }

  .portfolioStage {
    position: sticky;
    top: 0;
    height: 100vh;
    display: grid;
    place-items: center;
    perspective: 500px; /* the less px value, the "closer" the wrapper is going to appear on screen*/
    overflow: hidden;
  }

  .cardContainer {
    /* border: 1px solid #aaa; */
    margin-right: -100dvw;
    margin-bottom: 25dvh; /* change if needed */
    display: grid;
    grid-auto-columns: 300px;
    grid-auto-flow: column;
    grid-gap: 2rem;
    /* overflow-x: auto; */

    @media (max-width: 640px) {
      margin-left: 25dvw; /* adjust */
    }
  }

  .cardGroup {
    /* border: 2px solid black; */
    margin: 0 auto; /* center the card groups */
  }

  .cardCategory {
    /* "Atkinson Hyperlegible", sans-serif; */
    font-family: "Libre Caslon Condensed", serif;
    font-weight: 500;
    font-size: 1.5rem;
    text-align: center;
    color: #fff;
    margin-bottom: 1rem;
  }

  /* is there a way to not make top / left or width / height based on px? */
  .card,
  .card:focus {
    /* card dimension approx 4.25/5.5 */
    width: var(--cardWidth);
    height: var(--cardHeight);
    margin-bottom: calc(var(--cardHeight) * -0.75);
    place-items: center;
    background-color: #fff;
    border-radius: 10px;
    z-index: 1;
    filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
    /* position: absolute;
    top: 50%;
    left: 50%;
    transform: translate3d(-50%, -50%, 0); */
  }

  .card img {
    width: var(--cardWidth);
    height: var(--cardHeight);
    object-fit: cover;
    border-radius: 10px;
  }

  .card:hover {
    outline: 3px solid rgba(56, 102, 65, 1);
  }

  .card:not(:last-child):hover {
    transform: translate3d(0, calc(var(--cardHeight) * -0.6), 0);
    transition: transform 0.5s ease-in-out;
  }

  /* controls horizontal scrolly*/
  @supports (scroll-timeline: --swipe block) and (animation-timeline: --swipe) {
    .portfolioWrapper {
      scroll-timeline: --swipe block;
    }

    .cardContainer {
      animation: swipe 1s linear both;
      animation-timeline: --swipe;
    }
  }

  @keyframes swipe {
    from {
      transform: translate3d(0, 0, 0);
    }
    to {
      transform: translate3d(-100%, 0, 0);
    }
  }

  @media (prefers-reduced-motion: reduce) {
    .cardContainer {
      animation: none;
      transform: translate3d(0, 0, 0);
    }
  }
</style>
