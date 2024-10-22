<script>
  let data = '';
  let relativeFrequencies = {};

  function calculateRelativeFrequencies() {
    const values = data.split(',').map(item => item.trim());
    const totalCount = values.length;
    const frequencies = values.reduce((acc, val) => {
      acc[val] = (acc[val] || 0) + 1;
      return acc;
    }, {});
    relativeFrequencies = Object.entries(frequencies).reduce((acc, [key, value]) => {
      acc[key] = value / totalCount;
      return acc;
    }, {});
  }
</script>

<div class="card w-full bg-base-100 shadow-xl">
  <div class="card-body">
    <h2 class="card-title">Relative Frequency</h2>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Enter data (comma separated):</span>
      </label>
      <input type="text" bind:value={data} class="input input-bordered" placeholder="e.g., a,b,c,a,b,a,d,c" />
    </div>
    
    <div class="card-actions justify-end mt-4">
      <button class="btn btn-primary" on:click={calculateRelativeFrequencies}>Calculate</button>
    </div>
    
    <div class="mt-4">
      <h3 class="text-lg font-bold">Relative Frequencies:</h3>
      {#each Object.entries(relativeFrequencies) as [value, freq]}
        <p>{value}: {freq.toFixed(4)}</p>
      {/each}
    </div>
  </div>
</div>
