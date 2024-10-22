<script>
  let values = '';
  let probabilities = '';
  let expectedValue = 0;

  function calculateExpectedValue() {
    const valueArray = values.split(',').map(Number);
    const probArray = probabilities.split(',').map(Number);

    if (valueArray.length !== probArray.length) {
      alert('The number of values and probabilities must be the same.');
      return;
    }

    expectedValue = valueArray.reduce((sum, value, index) => sum + value * probArray[index], 0);
  }
</script>

<div class="card w-full bg-base-100 shadow-xl">
  <div class="card-body">
    <h2 class="card-title">Expected Value Calculator</h2>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Enter values (comma separated):</span>
      </label>
      <input type="text" bind:value={values} class="input input-bordered" placeholder="e.g., 1,2,3,4,5" />
    </div>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Enter probabilities (comma separated):</span>
      </label>
      <input type="text" bind:value={probabilities} class="input input-bordered" placeholder="e.g., 0.1,0.2,0.3,0.2,0.2" />
    </div>
    
    <div class="card-actions justify-end mt-4">
      <button class="btn btn-primary" on:click={calculateExpectedValue}>Calculate</button>
    </div>
    
    <div class="mt-4">
      <p class="text-lg">Expected Value: <span class="font-bold">{expectedValue}</span></p>
    </div>
  </div>
</div>
