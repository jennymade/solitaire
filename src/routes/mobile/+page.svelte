<div class="backgroundContainer">
  <div class="suitGrid">
    <div class="bigSuit">
      <div class="suitPosition"><div class="suitCard"></div></div>
      <div class="suitPosition"><div class="suitCard"></div></div>
      <div class="suitPosition"><div class="suitCard"></div></div>
    </div>
  </div>
</div>

<!-- keep component-related styles in the same page -->
<style>
  @import url("https://fonts.googleapis.com/css2?family=Commissioner:slnt,wght,FLAR,VOLM@-12..0,100..900,0..100,0..100&family=Faculty+Glyphic&family=Handjet:wght,ELSH@100..900,2&display=swap");

  /* REMINDER: Styling for Handjet
    font-family: "Handjet", sans-serif;
    font-optical-sizing: auto;
    font-weight: <weight>;
    font-style: normal;
    font-variation-settings:
    "ELGR" 1,
    "ELSH" 2; */

  .backgroundContainer {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 150vh;
    background-color: #386641; /* light green - dark green might be too intense*/
    border-radius: 10px;
    overflow-y: auto;
  }
  .portfolioHeader {
    font-family: "Handjet", sans-serif;
    font-size: 2rem;
    position: relative;
    text-align: center;
  }
  .key {
    font-family: "Handjet", sans-serif;
    font-size: 1.5rem;
    position: absolute;
    top: 10px;
    left: 50%;
    transform: translate3d(0, -50%, 0);
  }
  .otherWorkHeader {
    font-family: "Handjet", sans-serif;
    font-size: 2rem;
    position: relative;
    top: 66vh;
  }
  /* suit and suitCard should be the same size */
  .suit {
    width: 20vw;
    max-width: 375px;
    height: 300px;
    border-radius: 10px;
    background-color: #a7c9ae; /* light green */
    opacity: 0.33;
    /* padding: 10px; */
  }
  .projectColumn {
    margin-top: 25px;
    display: flex;
    flex-wrap: flex;
    flex-direction: column;
    gap: 0;
  }
  /* can you move card up via negative margin top */
  /* or keep card css via negative margin bottom */
  /* .projectColumn > .suitCard:not(:first-child) {
    margin-top: -10px;
  } */

  .suitGrid {
    position: sticky;
    top: 0;
    height: 100vh;
    place-items: center;
    perspective: 1000px;
    overflow: hidden;
  }
  .bigSuit {
    position: relative;
    width: 0;
    height: 0;
    transform-style: preserve-3d;
  }
  .suitPosition {
    position: absolute;
    top: 0;
    left: 0;
    transform: translate3d(var(--x), 0, var(--z));
    transform-style: preserve-3d;
  }
  .suitCard {
    /* can you make margin-bottom dependent on number of suitCards in the column? */
    z-index: 1;
    /* margin-bottom: -85%; */
    width: 375px;
    height: 525px;
    background-color: white; /* light green */
    border-radius: 10px;
    filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
    /* transform: rotateY(var(--face)); */
    backface-visibility: hidden;

    p {
      text-align: center;
      font-family: "Handjet", sans-serif;
    }
  }

  /* Coordinates around an oval in the X-Z plane */
  .suitPosition:nth-child(1) {
    --x: 0px;
    --z: 260px;
    --face: 0deg;
  }
  .suitPosition:nth-child(2) {
    --x: 156px;
    --z: 184px;
    --face: 45deg;
  }
  .suitPosition:nth-child(3) {
    --x: 220px;
    --z: 0px;
    --face: 90deg;
  }
  @supports (scroll-timeline: --rack block) and (animation-timeline: --rack) {
    .backgroundContainer {
      scroll-timeline: --rack block;
    }

    .bigSuit {
      animation: card-turn 1s linear both;
      animation-timeline: --rack;
    }
  }

  @keyframes card-turn {
    from {
      transform: rotate3d(0, 1, 0, 0deg);
    }
    to {
      transform: rotate3d(0, 1, 0, 1turn);
    }
  }

  @media (prefers-reduced-motion: reduce) {
    .bigSuit {
      animation: none;
      transform: rotate3d(0, 1, 0, 0deg);
    }
  }

  .suitCard:hover,
  .suitCard:focus {
    outline: 3px solid #ffd700;
  }

  .cardRotate {
    transform: rotate3d(0, 1, 0, 35deg);
  }

  .cardRotateTwo {
    transform: rotate3d(0, 1, 0, 120deg);
  }

  p {
    text-align: center;
    font-family: "Handjet", sans-serif;
    font-size: 2.5rem;
    font-optical-sizing: auto;
    font-weight: 400;
    font-style: normal;
    font-variation-settings: "ELGR" 1;
    font-weight: 400;
    font-style: normal;
  }
  .suitCategory {
    font-size: 1.5rem;
    font-weight: 400;
    padding: 0 1rem;
  }
</style>
