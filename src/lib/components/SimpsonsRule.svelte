<script>
  let a = 0;
  let b = 0;
  let n = 0;
  let func = '';
  let result = 0;

  function calculateSimpsonsRule() {
    try {
      const f = new Function('x', `return ${func}`);
      const h = (b - a) / n;
      let sum = f(a) + f(b);
      for (let i = 1; i < n; i++) {
        const x = a + i * h;
        sum += i % 2 === 0 ? 2 * f(x) : 4 * f(x);
      }
      result = (h / 3) * sum;
    } catch (error) {
      result = "Error: Invalid function or parameters";
    }
  }
</script>

<div class="card w-full bg-base-100 shadow-xl">
  <div class="card-body">
    <h2 class="card-title">Simpson's Rule</h2>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Function f(x):</span>
      </label>
      <input type="text" bind:value={func} class="input input-bordered" placeholder="e.g., Math.sin(x)" />
    </div>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Lower bound (a):</span>
      </label>
      <input type="number" bind:value={a} class="input input-bordered" />
    </div>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Upper bound (b):</span>
      </label>
      <input type="number" bind:value={b} class="input input-bordered" />
    </div>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Number of intervals (n, must be even):</span>
      </label>
      <input type="number" bind:value={n} class="input input-bordered" step="2" />
    </div>
    
    <div class="card-actions justify-end mt-4">
      <button class="btn btn-primary" on:click={calculateSimpsonsRule}>Calculate</button>
    </div>
    
    <div class="mt-4">
      <p class="text-lg">Result: <span class="font-bold">{result}</span></p>
    </div>
  </div>
</div>
