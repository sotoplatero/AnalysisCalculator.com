<script>
  let initialX = 0;
  let initialY = 0;
  let targetX = 0;
  let stepSize = 0;
  let derivative = '';
  let result = [];

  function calculateEulersMethod() {
    try {
      const f = new Function('x', 'y', `return ${derivative}`);
      let x = initialX;
      let y = initialY;
      result = [{x, y}];

      while (x < targetX) {
        const slope = f(x, y);
        y += slope * stepSize;
        x += stepSize;
        result.push({x, y});
      }
    } catch (error) {
      result = [{x: 'Error', y: 'Invalid function or parameters'}];
    }
  }
</script>

<div class="card w-full bg-base-100 shadow-xl">
  <div class="card-body">
    <h2 class="card-title">Euler's Method</h2>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Derivative (dy/dx):</span>
      </label>
      <input type="text" bind:value={derivative} class="input input-bordered" placeholder="e.g., x + y" />
    </div>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Initial x:</span>
      </label>
      <input type="number" bind:value={initialX} class="input input-bordered" />
    </div>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Initial y:</span>
      </label>
      <input type="number" bind:value={initialY} class="input input-bordered" />
    </div>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Target x:</span>
      </label>
      <input type="number" bind:value={targetX} class="input input-bordered" />
    </div>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Step size:</span>
      </label>
      <input type="number" bind:value={stepSize} class="input input-bordered" />
    </div>
    
    <div class="card-actions justify-end mt-4">
      <button class="btn btn-primary" on:click={calculateEulersMethod}>Calculate</button>
    </div>
    
    <div class="mt-4">
      <h3 class="text-lg font-bold">Results:</h3>
      <div class="overflow-x-auto">
        <table class="table w-full">
          <thead>
            <tr>
              <th>x</th>
              <th>y</th>
            </tr>
          </thead>
          <tbody>
            {#each result as {x, y}}
              <tr>
                <td>{typeof x === 'number' ? x.toFixed(4) : x}</td>
                <td>{typeof y === 'number' ? y.toFixed(4) : y}</td>
              </tr>
            {/each}
          </tbody>
        </table>
      </div>
    </div>
  </div>
</div>
