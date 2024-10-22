<script>
  let data = '';
  let frequencies = {};

  function calculateFrequencies() {
    const values = data.split(',').map(item => item.trim());
    frequencies = values.reduce((acc, val) => {
      acc[val] = (acc[val] || 0) + 1;
      return acc;
    }, {});
  }
</script>

<div class="card w-full bg-base-100 shadow-xl">
  <div class="card-body">
    <h2 class="card-title">Frequency Calculator</h2>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Enter data (comma separated):</span>
      </label>
      <input type="text" bind:value={data} class="input input-bordered" placeholder="e.g., a,b,c,a,b,a,d,c" />
    </div>
    
    <div class="card-actions justify-end mt-4">
      <button class="btn btn-primary" on:click={calculateFrequencies}>Calculate</button>
    </div>
    
    <div class="mt-4">
      <h3 class="text-lg font-bold">Frequencies:</h3>
      {#each Object.entries(frequencies) as [value, freq]}
        <p>{value}: {freq}</p>
      {/each}
    </div>
  </div>
</div>
