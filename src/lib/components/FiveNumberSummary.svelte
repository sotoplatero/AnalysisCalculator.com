<script>
  let data = '';
  let min = 0;
  let q1 = 0;
  let median = 0;
  let q3 = 0;
  let max = 0;

  function calculateFiveNumberSummary() {
    const values = data.split(',').map(Number).sort((a, b) => a - b);
    min = values[0];
    max = values[values.length - 1];
    median = values[Math.floor(values.length / 2)];
    q1 = values[Math.floor(values.length / 4)];
    q3 = values[Math.floor(3 * values.length / 4)];
  }
</script>

<div class="card w-full bg-base-100 shadow-xl">
  <div class="card-body">
    <h2 class="card-title">Five Number Summary</h2>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Enter data (comma separated):</span>
      </label>
      <input type="text" bind:value={data} class="input input-bordered" placeholder="e.g., 1,2,3,4,5,6,7,8,9,10" />
    </div>
    
    <div class="card-actions justify-end mt-4">
      <button class="btn btn-primary" on:click={calculateFiveNumberSummary}>Calculate</button>
    </div>
    
    <div class="mt-4">
      <p class="text-lg">Minimum: <span class="font-bold">{min}</span></p>
      <p class="text-lg">Q1: <span class="font-bold">{q1}</span></p>
      <p class="text-lg">Median: <span class="font-bold">{median}</span></p>
      <p class="text-lg">Q3: <span class="font-bold">{q3}</span></p>
      <p class="text-lg">Maximum: <span class="font-bold">{max}</span></p>
    </div>
  </div>
</div>
