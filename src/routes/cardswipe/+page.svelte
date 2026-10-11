<!-- jenny note: remember to add: aria-label, aria-describedby -->
<svelte:head>
  <title>it's jennymade</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link
    href="https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&display=swap"
    rel="stylesheet"
  />
</svelte:head>
<div class="portfolioWrapper" role="region">
  <div class="portfolioHeaderSection">
    <h1 class="portfolioHeader">
      <span>♦</span> it's <span class="jenny">jenny</span>made <span>♦</span>
    </h1>
  </div>
  <div class="scrollWrapper__run">
    <div class="portfolioStage">
      <div class="cardContainer">
        <div class="cardGroup">
          <h2 class="cardCategory">ui/ux design</h2>
          <div class="card first">Item 1</div>
          <div class="card second">Item 2</div>
          <div class="card third">Item 3</div>
          <div class="card fourth">Item 4</div>
        </div>
        <div class="cardGroup">
          <h2 class="cardCategory">data viz</h2>
          <div class="card first"></div>
          <div class="card second">Item 2</div>
          <div class="card third">Item 3</div>
        </div>
        <div class="cardGroup">
          <h2 class="cardCategory">illustration</h2>
          <div class="card first">Item 1</div>
          <div class="card second">Item 2</div>
          <div class="card third">Item 3</div>
        </div>
        <div class="cardGroup">
          <h2 class="cardCategory">reporting</h2>
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
    font-family: "Instrument Serif", serif, "Courier New", Courier, monospace;
    font-weight: 400;
    font-style: normal;
  }

  .portfolioWrapper {
    height: 100vh;
    overflow-y: auto;
    background-color: rgba(56, 102, 65, 0.75); /* solitaire green */
    border-radius: 10px;
  }

  .portfolioHeader {
    color: #fff;
    font-size: 3rem;

    .jenny {
      font-size: 3rem;
      letter-spacing: 0.2rem;
      font-style: italic;
      vertical-align: baseline;
    }

    span {
      font-size: 1rem;
      vertical-align: middle;
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
    font-family: "Instrument Serif", serif;
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
    object-fit: scale-down !important;
  }

  .card:not(:last-child):hover {
    outline: 3px solid rgba(56, 102, 65, 1);
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
