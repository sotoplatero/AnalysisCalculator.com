<script>
  let lambda = 0;
  let k = 0;
  let result = 0;

  function calculatePoissonProbability() {
    const factorial = (n) => n <= 1 ? 1 : n * factorial(n - 1);
    result = (Math.pow(lambda, k) * Math.exp(-lambda)) / factorial(k);
  }
</script>

<div class="card w-full bg-base-100 shadow-xl">
  <div class="card-body">
    <h2 class="card-title">Poisson Distribution Calculator</h2>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Enter lambda (average rate):</span>
      </label>
      <input type="number" bind:value={lambda} class="input input-bordered" />
    </div>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Enter k (number of occurrences):</span>
      </label>
      <input type="number" bind:value={k} class="input input-bordered" />
    </div>
    
    <div class="card-actions justify-end mt-4">
      <button class="btn btn-primary" on:click={calculatePoissonProbability}>Calculate</button>
    </div>
    
    <div class="mt-4">
      <p class="text-lg">Probability: <span class="font-bold">{result}</span></p>
    </div>
  </div>
</div>
