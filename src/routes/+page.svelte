<div class="solitaireContainer">
  <h1 class="portfolioHeader">hi, i'm jenny</h1>
  <!-- <p class="key">key:</p> -->
  <div class="suitGrid">
    <div class="suit">
      <p>♥︎</p>
      <p class="suitCategory">Product design</p>
    </div>
    <div class="suit">
      <p>♤♠</p>
      <p class="suitCategory">Brand design and identity</p>
    </div>
    <div class="suit">
      <p>♣</p>
      <p class="suitCategory">Data analysis, reporting and visualization</p>
    </div>
    <div class="suit">
      <p>♦</p>
      <p class="suitCategory">Illustration work</p>
    </div>
    <div class="suit"><p>Misc</p></div>
    <div class="projectColumn">
      <div class="suitCard"></div>
      <div class="suitCard"></div>
      <div class="suitCard"></div>
    </div>
    <div class="projectColumn">
      <div class="suitCard"></div>
      <div class="suitCard"></div>
      <div class="suitCard"></div>
    </div>
  </div>
  <p class="otherWorkHeader">other past work</p>
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

  .solitaireContainer {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 150vh;
    background-color: #386641; /* light green - dark green might be too intense*/
    border-radius: 10px;
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
  .suitGrid {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    column-gap: 25px;
    position: absolute;
    top: 10%;
    left: 50%;
    /* translate3d is least expensive for performance */
    transform: translate3d(-50%, 0, 0);
    margin: 0 auto;
  }
  /* suit and suitCard should be the same size */
  .suit {
    width: 15vw;
    max-width: 200px;
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
  .suitCard {
    /* can you make margin-bottom dependent on number of suitCards in the column? */
    z-index: 1;
    margin-bottom: -85%;
    width: 15vw;
    max-width: 200px;
    height: 300px;
    background-color: white; /* light green */
    border-radius: 10px;
    filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
  }
  .suitCard:hover,
  .suitCard:focus {
    outline: 3px solid #ffd700;
  }
  .suitCard:not(:first-child):hover,
  .suitCard:not(:first-child):focus {
    transform: translate3d(0, 50px, 0);
    transition: transform 500ms ease-in-out;
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
