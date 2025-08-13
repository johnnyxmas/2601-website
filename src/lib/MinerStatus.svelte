<script>
  let cpuUsage = 0;
  let gpuUsage = 0;
  
  function randomizeUsage() {
    cpuUsage = Math.floor(Math.random() * 100);
    gpuUsage = Math.floor(Math.random() * 100);
    setTimeout(randomizeUsage, 1000 + Math.random() * 2000);
  }
  
  randomizeUsage();
</script>

<div class="miner-status">
  <div class="status-bar">
    <span>MEMECOIN MINER v1.0</span>
    <span>CPU: {cpuUsage}%</span>
    <span>GPU: {gpuUsage}%</span>
    <span>HASH: {(cpuUsage * gpuUsage * 100).toLocaleString()}</span>
  </div>
</div>

<style>
  .miner-status {
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    background: #111;
    color: lime;
    font-family: monospace;
    padding: 5px;
    border-top: 1px solid #333;
  }
  
  .status-bar {
    display: flex;
    justify-content: center;
    gap: 20px;
    padding: 0 10px;
  }
</style>