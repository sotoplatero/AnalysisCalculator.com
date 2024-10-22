<script>
  let x1 = 0;
  let y1 = 0;
  let x2 = 0;
  let y2 = 0;
  let x = 0;
  let result = 0;

  function interpolate() {
    if (x2 - x1 !== 0) {
      result = y1 + ((x - x1) * (y2 - y1)) / (x2 - x1);
    } else {
      result = "Error: x2 - x1 cannot be zero";
    }
  }
</script>

<div class="card w-96 bg-base-100 shadow-xl">
  <div class="card-body">
    <h2 class="card-title">Linear Interpolation</h2>

    <div class="form-control">
      <label class="label">
        <span class="label-text">x1:</span>
        <input type="number" bind:value={x1} class="input input-bordered w-full" />
      </label>
    </div>
    <div class="form-control">
      <label class="label">
        <span class="label-text">y1:</span>
        <input type="number" bind:value={y1} class="input input-bordered w-full" />
      </label>
    </div>
    <div class="form-control">
      <label class="label">
        <span class="label-text">x2:</span>
        <input type="number" bind:value={x2} class="input input-bordered w-full" />
      </label>
    </div>
    <div class="form-control">
      <label class="label">
        <span class="label-text">y2:</span>
        <input type="number" bind:value={y2} class="input input-bordered w-full" />
      </label>
    </div>
    <div class="form-control">
      <label class="label">
        <span class="label-text">x (point to interpolate):</span>
        <input type="number" bind:value={x} class="input input-bordered w-full" />
      </label>
    </div>

    <div class="card-actions justify-end">
      <button class="btn btn-primary" on:click={interpolate}>Calculate</button>
    </div>

    <div class="mt-4">
      <p class="text-lg">Result: <span class="font-bold">{result}</span></p>
    </div>
  </div>
</div>
