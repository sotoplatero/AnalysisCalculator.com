<script>
  let data = '';
  let outliers = [];

  function calculateOutliers() {
    const values = data.split(',').map(Number).sort((a, b) => a - b);
    const q1 = values[Math.floor(values.length / 4)];
    const q3 = values[Math.floor(3 * values.length / 4)];
    const iqr = q3 - q1;
    const lowerBound = q1 - 1.5 * iqr;
    const upperBound = q3 + 1.5 * iqr;
    outliers = values.filter(v => v < lowerBound || v > upperBound);
  }
</script>

<div class="card w-full bg-base-100 shadow-xl">
  <div class="card-body">
    <h2 class="card-title">Outlier</h2>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Enter data (comma separated):</span>
      </label>
      <input type="text" bind:value={data} class="input input-bordered" placeholder="e.g., 1,2,3,4,5,100" />
    </div>
    
    <div class="card-actions justify-end mt-4">
      <button class="btn btn-primary" on:click={calculateOutliers}>Calculate</button>
    </div>
    
    <div class="mt-4">
      <h3 class="text-lg font-bold">Outliers:</h3>
      <p>{outliers.join(', ') || 'No outliers found'}</p>
    </div>
  </div>
</div>
