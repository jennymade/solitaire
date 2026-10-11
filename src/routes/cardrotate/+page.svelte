<h2 id="scrollHeading">Clothing rack</h2>
<p id="scrollInstructions">
  Press tab to focus on the closet rack, then use your up and down arrows or
  page up and page down to rotate the rack and see all items!
</p>
<div
  class="scrollWrapper"
  tabindex="0"
  role="region"
  aria-label="Clothing rack"
  aria-describedby="scrollInstructions"
>
  <div class="scrollWrapper__run">
    <div class="rack-stage">
      <div class="rack-rotor">
        <div class="hanger-position">
          <div class="hanger-card">Item 1</div>
        </div>
        <div class="hanger-position">
          <div class="hanger-card">Item 2</div>
        </div>
        <div class="hanger-position">
          <div class="hanger-card">Item 3</div>
        </div>
        <div class="hanger-position">
          <div class="hanger-card">Item 4</div>
        </div>
        <div class="hanger-position">
          <div class="hanger-card">Item 5</div>
        </div>
        <div class="hanger-position">
          <div class="hanger-card">Item 6</div>
        </div>
        <div class="hanger-position">
          <div class="hanger-card">Item 7</div>
        </div>
        <div class="hanger-position"><div class="hanger-card">Item 8</div></div>
      </div>
    </div>
  </div>
</div>

<style>
  :root {
    /* define variables here */
    --numItems: 8;
    /* math: divide 360deg by num of items to get the angle between each item */
    --itemAngle: calc(360deg / var(--numItems));
  }

  .scrollWrapper {
    height: 100vh;
    overflow-y: auto;
  }

  .scrollWrapper__run {
    height: 500vh; /* Longer track means more scroll to complete the turn */
  }

  .rack-stage {
    position: sticky;
    top: 0;
    height: 100vh;
    display: grid;
    place-items: center;
    perspective: 500px; /* the less px value, the "closer" the wrapper is going to appear on screen*/
    overflow: hidden;
  }

  .rack-rotor {
    position: relative;
    width: 0;
    height: 0;
    transform-style: preserve-3d;
  }

  .hanger-position,
  .hanger-position:focus {
    position: absolute;
    top: 0;
    left: 0;
    transform-style: preserve-3d;
    transform: translate3d(
      var(--x),
      0,
      var(--z)
    ); /* you define x and z in each nth-child specific css */
  }

  /* is there a way to not make top / left or width / height based on px? */
  .hanger-card,
  .hanger-card:focus {
    position: absolute;
    top: -120px;
    left: -60px;
    width: 120px;
    height: 220px;
    display: grid;
    place-items: center;
    background: #fff;
    border: 1px solid #aaa;
    transform: rotateY(
      var(--face)
    ); /* you define face in each nth-child specific css */
    backface-visibility: hidden;
  }

  /* coordinates around an oval in the X-Z plane */
  /* rotates clockwise */
  /* figure out how x and z relate to height + width of card */
  .hanger-position:nth-child(1) {
    --x: 0px;
    --z: 260px;
    --face: 0deg;
  }
  .hanger-position:nth-child(2) {
    --x: -156px;
    --z: 184px;
    --face: calc(var(--itemAngle) * -1); /* 315deg */
  }
  .hanger-position:nth-child(3) {
    --x: -220px;
    --z: 0px;
    --face: calc(var(--itemAngle) * -2); /* 270deg */
  }
  .hanger-position:nth-child(4) {
    --x: -156px;
    --z: -184px;
    --face: calc(var(--itemAngle) * -3); /* 225deg */
  }
  .hanger-position:nth-child(5) {
    --x: 0px;
    --z: -260px;
    --face: calc(var(--itemAngle) * -4); /* 180deg */
  }
  .hanger-position:nth-child(6) {
    --x: 156px;
    --z: -184px;
    --face: calc(var(--itemAngle) * -5); /* 135deg */
  }
  .hanger-position:nth-child(7) {
    --x: 220px;
    --z: 0px;
    --face: calc(var(--itemAngle) * -6); /* 90deg */
  }
  .hanger-position:nth-child(8) {
    --x: 156px;
    --z: 184px;
    --face: calc(var(--itemAngle) * -7); /* 45deg */
  }

  @supports (scroll-timeline: --rack block) and (animation-timeline: --rack) {
    .scrollWrapper {
      scroll-timeline: --rack block;
    }

    .rack-rotor {
      animation: rack-turn 1s linear both;
      animation-timeline: --rack;
    }
  }

  @keyframes rack-turn {
    from {
      transform: rotate3d(0, 1, 0, 0deg);
    }
    to {
      transform: rotate3d(0, 1, 0, 1turn);
    }
  }

  @media (prefers-reduced-motion: reduce) {
    .rack-rotor {
      animation: none;
      transform: rotate3d(0, 1, 0, 0deg);
    }
  }
</style>
