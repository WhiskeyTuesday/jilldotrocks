<script lang="ts">
  import tweet from '#lib/tweet.png';

  import { onMount } from 'svelte';

  let cubeRotation = 0;
  let swirl = 0;

  onMount(() => {
    const interval = setInterval(() => {
      cubeRotation = (cubeRotation + 1) % 360;
      swirl = (swirl + 2) % 360;
    }, 50);

    return () => clearInterval(interval);
  });
</script>

<svelte:head>
  <title>jill.rocks</title>
  <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap" rel="stylesheet">
</svelte:head>

<main>
  <header>
    <div class="logo">
      <span class="cube" style="transform: rotateY({cubeRotation}deg)">▢</span>
      <h1>jill.rocks</h1>
    </div>
    <!--
    <nav>
      <ul>
        <li><a href="#psa">PSA</a></li>
        <li><a href="#tips">Tips</a></li>
        <li><a href="#about">About</a></li>
      </ul>
    </nav>
    -->
  </header>

  <section id="psa" class="hero">
    <div class="dreamcast-swirl" style="transform: rotate({swirl}deg)"></div>
    <h2>PUBLIC SERVICE ANNOUNCEMENT</h2>
    <p class="tagline">Don't let your dream domain slip away!</p>
    <p class="message">Never post about domain names you want to register publicly before securing them.</p>
    <p class="message">Some unscrupulous person could register it out from under you and make a whole website just to make fun of you. You wouldn't want that.</p>
    <div class="cta-container">
      <button class="cta cta-a">H</button>
      <button class="cta cta-b">A</button>
      <button class="cta cta-x">H</button>
      <button class="cta cta-y">A</button>
    </div>
  </section>

  <section id="tips" class="features">
    <h2>Domain Protection Tips</h2>
    <div class="vmu-container">
      <div class="vmu">
        <div class="vmu-screen">Research privately</div>
      </div>
      <div class="vmu">
        <div class="vmu-screen">Register immediately</div>
      </div>
      <div class="vmu">
        <div class="vmu-screen">Use trusted registrars</div>
      </div>
      <div class="vmu">
        <div class="vmu-screen">Enable domain privacy</div>
      </div>
    </div>
  </section>

  <section id="about" class="about">
    <h2>Whomp whomp</h2>
    <img src={tweet} alt="Whomp whomp"/>
    <div class="tech-circle"></div>
  </section>

  <footer>
    <p>© 2025</p>
    <p class="retro-text">
      jill.rocks is powered by
      <a href="https://www.lcc.solutions">The Lifestyle Computing Company</a>
      and maintained by <a href="https://www.elijasorensen.com">Elija Sorensen</a>
    </p>
    <p class="retro-text">Be good to each other stay cool</p>

  </footer>
</main>

<style>
  :global(body) {
    margin: 0;
    font-family: 'Press Start 2P', cursive;
    background-color: #000;
    color: #fff;
    line-height: 1.6;
  }

  main {
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
  }

  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 0;
  }

  img {
    display: block;
    margin: 0 auto;
    max-width: 100%;
  }

  .logo {
    display: flex;
    align-items: center;
    font-size: 24px;
    font-weight: bold;
  }

  .cube {
    display: inline-block;
    font-size: 36px;
    margin-right: 10px;
    color: #6a5acd;
  }

  nav ul {
    display: flex;
    list-style-type: none;
    padding: 0;
  }

  nav ul li {
    margin-left: 20px;
  }

  nav ul li a {
    color: #fff;
    text-decoration: none;
    font-weight: bold;
    text-transform: uppercase;
  }

  .hero {
    text-align: center;
    padding: 60px 0;
    background: linear-gradient(45deg, #6a5acd, #4b0082);
    border-radius: 20px;
    margin-bottom: 40px;
    position: relative;
    overflow: hidden;
  }

  .dreamcast-swirl {
    position: absolute;
    top: -50px;
    left: -50px;
    width: 100px;
    height: 100px;
    background: conic-gradient(from 0deg, #ff7f00, #ff7f00 25%, #0080ff 25%, #0080ff 50%, #ff7f00 50%, #ff7f00 75%, #0080ff 75%);
    border-radius: 50%;
    opacity: 0.6;
  }

  h2 {
    font-size: 28px;
    margin-bottom: 20px;
    text-transform: uppercase;
  }

  .tagline {
    font-size: 20px;
    margin-bottom: 20px;
  }

  .message {
    font-size: 16px;
    margin: 4rem;
    margin-bottom: 30px;
  }

  .cta-container {
    display: flex;
    justify-content: center;
    gap: 10px;
  }

  .cta {
    width: 60px;
    height: 60px;
    border: none;
    border-radius: 50%;
    font-size: 18px;
    font-weight: bold;
    cursor: pointer;
    transition: transform 0.3s ease;
  }

  .cta:hover {
    transform: scale(1.1);
  }

  .cta-a { background-color: #00ff00; }
  .cta-b { background-color: #ff0000; }
  .cta-x { background-color: #0000ff; }
  .cta-y { background-color: #ffff00; }

  .features {
    background-color: #4b0082;
    padding: 40px;
    border-radius: 20px;
    margin-bottom: 40px;
  }

  .vmu-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 20px;
  }

  .vmu {
    background-color: #1e90ff;
    border-radius: 10px;
    padding: 20px;
    text-align: center;
  }

  .vmu-screen {
    background-color: #98fb98;
    color: #000;
    padding: 10px;
    border-radius: 5px;
    font-size: 12px;
  }

  .about {
    text-align: center;
    margin-bottom: 40px;
    position: relative;
  }

  .tech-circle {
    position: absolute;
    top: -20px;
    right: -20px;
    width: 100px;
    height: 100px;
    border: 2px solid #00ffff;
    border-radius: 50%;
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0% { transform: scale(1); opacity: 1; }
    50% { transform: scale(1.1); opacity: 0.7; }
    100% { transform: scale(1); opacity: 1; }
  }

  footer {
    text-align: center;
    padding: 20px 0;
    font-size: 12px;
  }

  .retro-text {
    color: #ff7f00;
    font-size: 10px;
    margin-top: 10px;
  }

  @media (max-width: 768px) {
    header {
      flex-direction: column;
    }

    nav ul {
      margin-top: 20px;
    }

    .hero {
      padding: 40px 20px;
    }

    h2 {
      font-size: 24px;
    }

    .tagline {
      font-size: 18px;
    }

    .message {
      font-size: 14px;
    }

    .cta {
      width: 50px;
      height: 50px;
      font-size: 16px;
    }
  }
</style>
