<script>
  import MinerStatus from './lib/MinerStatus.svelte';
  
  // Snax stats data
  const snaxStats = [
    { label: "Chips Chomped", value: "42 billion" },
    { label: "Cookies Dunked", value: "3.7 trillion" },
    { label: "Pizzas Destroyed", value: "350 million daily" }
  ]
  
  let hours = 0;
</script>

<main>
  <h1>2601: THE SNACKER QUARTERLY</h1>
  <h2>Snack the planet!!!</h2>

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
  :global(body) {
    background-color: #0a0a12;
    color: #00ff9d;
    font-family: 'Courier New', monospace;
    margin: 0;
    padding: 2rem;
  }

  h1 {
    color: #ff00aa;
    text-shadow: 0 0 10px #ff00aa;
    font-size: 3rem;
    margin-bottom: 0.5rem;
  }

  h2 {
    color: #00f0ff;
    text-shadow: 0 0 5px #00f0ff;
    margin-top: 0;
  }

  .cyber-card {
    border: 2px solid #ff00aa;
    padding: 2rem;
    margin: 2rem 0;
    box-shadow: 0 0 15px #ff00aa80;
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
  }

  .cyber-button:hover {
    background: #ff00aa;
    box-shadow: 0 0 15px #ff00aa;
  }

  .stats-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2rem;
    margin: 3rem 0;
  }

  .stat-item {
    border: 1px solid #00f0ff;
    padding: 1rem;
  }

  .stat-value {
    color: #ff00aa;
    font-size: 2rem;
    font-weight: bold;
  }

  .cyber-quote {
    font-style: italic;
    border-left: 3px solid #00f0ff;
    padding-left: 1rem;
    margin: 3rem 0;
  }

  .snax-of-month, .hacker-jokes, .snax-calculator {
    border: 1px dashed #ff00aa;
    padding: 1.5rem;
    margin: 2rem 0;
  }

  .snax-name {
    color: #00f0ff;
    font-size: 1.5rem;
    font-weight: bold;
    margin-bottom: 0.5rem;
  }

  .joke {
    margin: 1rem 0;
    padding: 1rem;
    background: #0a0a20;
  }

  .snax-calculator input {
    background: #0a0a20;
    border: 1px solid #00f0ff;
    color: #00ff9d;
    padding: 0.5rem;
    margin: 1rem 0;
    width: 100%;
    max-width: 300px;
  }

  .result {
    color: #ff00aa;
    font-size: 1.2rem;
    margin: 1rem 0;
  }
</style>
