<script>
  import { onMount } from 'svelte';

  let canvas;
  let ctx;
  const chars = "アカサタナハマヤラワイキシチニヒミリウクスツヌフムユルエケセテネヘメレオコソトノホモヨロヲ";
  const fontSize = 18;
  let columns = 0;
  let drops = [];
  let animationId;
  let lastTime = 0;
  const frameRate = 30;
  const frameInterval = 1000 / frameRate;
  
  onMount(() => {
    // Set up canvas
    function resize() {
      const width = window.innerWidth;
      const height = window.innerHeight;
      
      if (Math.abs(canvas.width - width) > 50 || Math.abs(canvas.height - height) > 50) {
        canvas.width = width;
        canvas.height = height;
        columns = Math.floor(width / fontSize);
        drops = Array(columns).fill(1);
      }
    }
    
    resize();
    const resizeObserver = new ResizeObserver(resize);
    resizeObserver.observe(document.body);
    
    ctx = canvas.getContext('2d', { alpha: false });
    ctx.font = `${fontSize}px monospace`;
    ctx.textAlign = 'center';

    function animate(timestamp) {
      if (!lastTime) lastTime = timestamp;
      const deltaTime = timestamp - lastTime;
      
      if (deltaTime > frameInterval) {
        draw();
        lastTime = timestamp - (deltaTime % frameInterval);
      }
      
      animationId = requestAnimationFrame(animate);
    }
    
    animationId = requestAnimationFrame(animate);
    
    return () => {
      cancelAnimationFrame(animationId);
      resizeObserver.disconnect();
    };
  });

  function draw() {
    ctx.fillStyle = 'rgba(0, 0, 0, 0.03)';
    ctx.fillRect(0, 0, canvas.width, canvas.height);
    
    ctx.fillStyle = '#00ff41';
    const charCount = chars.length;
    const heightThreshold = canvas.height / fontSize;
    
    for (let i = 0; i < drops.length; i++) {
      const charIndex = Math.floor(Math.random() * charCount);
      const x = i * fontSize;
      const y = drops[i] * fontSize;
      
      ctx.fillText(chars[charIndex], x, y);
      
      if (drops[i] > heightThreshold && Math.random() > 0.975) {
        drops[i] = 0;
      }
      drops[i]++;
    }
  }
</script>

<canvas bind:this={canvas} class="matrix-canvas"></canvas>

<style>
  .matrix-canvas {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -2;
    pointer-events: none;
  }
</style>