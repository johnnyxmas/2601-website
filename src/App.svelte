<svelte:head>
  <title>2601 - Snack-Fueled Hacker Collective</title>
  <meta name="description" content="Join snack-fueled hackers, cyberpunks and 2600 magazine fans in our mission to snack the planet. Chips, code and chaos since 2601.">
  <meta name="keywords" content="hacker snacks, cyberpunk food, 2600 magazine, snack technology, hacker culture">
  
  <!-- Open Graph / Facebook -->
  <meta property="og:type" content="website">
  <meta property="og:url" content="https://omgsnax.com/">
  <meta property="og:title" content="2601 - Snack-Fueled Hacker Collective">
  <meta property="og:description" content="Join snack-fueled hackers in our mission to snack the planet">
  <meta property="og:image" content="https://omgsnax.com/assets/banner.jpg">

  <!-- Twitter -->
  <meta property="twitter:card" content="summary_large_image">
  <meta property="twitter:url" content="https://omgsnax.com/">
  <meta property="twitter:title" content="2601 - Snack-Fueled Hacker Collective">
  <meta property="twitter:description" content="Join snack-fueled hackers in our mission to snack the planet">
  <meta property="twitter:image" content="https://omgsnax.com/assets/banner.jpg">
</svelte:head>

<script>
  import MinerStatus from './lib/MinerStatus.svelte';
  import MatrixBackground from './lib/MatrixBackground.svelte';
  
  // Snax stats data
  const snaxStats = [
    { label: "Chips Chomped", value: "42 billion" },
    { label: "Cookies Dunked", value: "3.7 trillion" },
    { label: "Pizzas Destroyed", value: "350 million daily" }
  ]
  
  let hours = 0;
</script>

<MatrixBackground />

<div class="overlay"></div>

<main>
  <img src="assets/banner.jpg" alt="Snack Banner" class="banner-image">
  <h1>Snack the Planet!!!</h1>

  <div class="cyber-card">
    <h3>JOIN OUR SNACK-FUELED HACKER DISCORD</h3>
    <a href="https://discord.gg/W5GQm46ret" class="cyber-button">
      ENTER THE SNACKVERSE
    </a>
  </div>

  <div class="stats-grid">
    {#each snaxStats as stat}
      <div class="stat-item">
        <div class="stat-value">{stat.value}</div>
        <div class="stat-label">{stat.label}</div>
      </div>
    {/each}
  </div>

  <div class="cyber-quote">
    "In the year 2601, only two things matter: 1337 code and 1,337 snax."
  </div>

  <div class="snax-of-month">
    <h3>SN4X OF THE MONTH</h3>
    <div class="snax-item">
      <div class="snax-name">N3ON-CH3ETOS</div>
      <div class="snax-desc">Glows under blacklight. Contains 9001% daily recommended hacking power and uranium.</div>
    </div>
  </div>
</main>

<MinerStatus />

<style>
  .banner-image {
    width: 90%;
    max-width: 600px;
    margin: 0 auto 1rem;
    display: block;
    border: 3px solid #5a0d7a;
    box-shadow: 0 0 20px #9c27b0, 0 0 30px #9c27b0;
    border-radius: 5px;
    position: relative;
    z-index: 1000;
    height: auto;
  }

  @media (max-width: 768px) {
    .banner-image {
      width: 95%;
      margin-bottom: 0.5rem;
    }
  }

  :global(body) {
    color: #00ff9d;
    font-family: 'Courier New', monospace;
    margin: 0;
    padding: 1rem;
    overflow-x: hidden;
  }

  @media (max-width: 768px) {
    :global(body) {
      padding: 0.5rem;
    }
  }

  .overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background-color: rgba(0, 0, 0, 0.5);
    z-index: -1;
    pointer-events: none;
  }

  main {
    position: relative;
    z-index: 1;
  }

  h1 {
    color: #ff00aa;
    text-shadow: 0 0 10px #ff00aa;
    font-size: clamp(1.5rem, 8vw, 3rem);
    margin-bottom: 0.5rem;
    background-color: rgba(0, 0, 0, 0.7);
    padding: 1rem;
    display: inline-block;
    text-align: center;
    width: 100%;
    box-sizing: border-box;
  }

  .cyber-card {
    border: 2px solid #ff00aa;
    padding: 1.5rem;
    margin: 1rem 0;
    box-shadow: 0 0 15px #ff00aa80;
    background-color: rgba(0, 0, 0, 0.7);
  }

  @media (max-width: 768px) {
    .cyber-card {
      padding: 1rem;
      margin: 0.5rem 0;
    }
  }

  .cyber-button {
    display: inline-block;
    background: #00f0ff;
    color: #0a0a12;
    padding: 1rem 2rem;
    text-decoration: none;
    font-weight: bold;
    margin-top: 1rem;
    transition: all 0.3s;
    min-width: 44px;
    min-height: 44px;
    text-align: center;
  }

  @media (max-width: 768px) {
    .cyber-button {
      padding: 0.8rem 1.5rem;
      font-size: 1rem;
      display: block;
      margin: 1rem auto;
    }
  }

  .cyber-button:hover {
    background: #ff00aa;
    box-shadow: 0 0 15px #ff00aa;
  }

  .stats-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1rem;
    margin: 2rem 0;
  }

  @media (max-width: 768px) {
    .stats-grid {
      grid-template-columns: 1fr;
      gap: 1rem;
      margin: 1rem 0;
    }
  }

  .stat-item {
    border: 1px solid #00f0ff;
    padding: 1rem;
    background-color: rgba(0, 0, 0, 0.7);
  }

  .stat-value {
    color: #ff00aa;
    font-size: 2rem;
    font-weight: bold;
  }

  .cyber-quote {
    font-style: italic;
    padding: 1rem;
    margin: 2rem 0;
    background-color: rgba(0, 0, 0, 0.7);
    font-size: clamp(0.9rem, 3vw, 1.1rem);
  }

  @media (max-width: 768px) {
    .cyber-quote {
      margin: 1rem 0;
      padding: 0.8rem;
    }
  }

  .snax-of-month {
    border: 1px dashed #ff00aa;
    padding: 1rem;
    margin: 1.5rem 0;
    background-color: rgba(0, 0, 0, 0.7);
  }

  @media (max-width: 768px) {
    .snax-of-month {
      padding: 0.8rem;
      margin: 1rem 0;
    }
  }

  .snax-name {
    color: #00f0ff;
    font-size: 1.5rem;
    font-weight: bold;
    margin-bottom: 0.5rem;
  }
</style>
