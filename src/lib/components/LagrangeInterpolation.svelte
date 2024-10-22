<script>
  import InterpolationBase from './InterpolationBase.svelte';
  
  let points = [];
  let x = 0;
  let result = 0;

  function interpolate() {
    // Implementar la lógica de interpolación de Lagrange aquí
    result = "Lagrange interpolation not implemented yet";
  }
</script>

<InterpolationBase title="Lagrange Interpolation Calculator" on:pointsUpdated={(e) => points = e.detail}>
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
