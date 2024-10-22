<script>
  import InterpolationBase from './InterpolationBase.svelte';
  
  let points = [];
  let x = 0;
  let result = 0;

  function interpolate() {
    if (points.length < 2) {
      result = "Error: Need at least 2 points for linear interpolation";
      return;
    }

    points.sort((a, b) => a.x - b.x);
    
    for (let i = 0; i < points.length - 1; i++) {
      if (x >= points[i].x && x <= points[i+1].x) {
        const x1 = points[i].x;
        const y1 = points[i].y;
        const x2 = points[i+1].x;
        const y2 = points[i+1].y;
        
        result = y1 + ((x - x1) * (y2 - y1)) / (x2 - x1);
        return;
      }
    }

    result = "Error: x is out of the range of given points";
  }
</script>

<InterpolationBase title="Linear Interpolation Calculator" on:pointsUpdated={(e) => points = e.detail}>
  <div class="form-control mt-4">
    <label class="label">
      <span class="label-text">x (point to interpolate):</span>
    </label>
    <input type="number" bind:value={x} class="input input-bordered w-full" />
  </div>

  <div class="card-actions justify-end mt-4">
    <button class="btn btn-primary" on:click={interpolate}>Calculate</button>
  </div>

  <div class="mt-4">
    <p class="text-lg">Result: <span class="font-bold">{result}</span></p>
  </div>
</InterpolationBase>
