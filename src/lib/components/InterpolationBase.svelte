<script>
  import { createEventDispatcher } from 'svelte';

  export let title = "Interpolation Calculator";
  let points = [];
  let pasteArea = '';
  const dispatch = createEventDispatcher();

  function handlePaste() {
    const lines = pasteArea.trim().split('\n');
    points = lines.map(line => {
      const [x, y] = line.split(/[,\s]+/).map(Number);
      return { x, y };
    }).filter(point => !isNaN(point.x) && !isNaN(point.y));
    pasteArea = '';
    dispatch('pointsUpdated', points);
  }

  function addPoint() {
    points = [...points, { x: 0, y: 0 }];
    dispatch('pointsUpdated', points);
  }

  function updatePoint(index, field, value) {
    points[index][field] = Number(value);
    points = points;
    dispatch('pointsUpdated', points);
  }

  function removePoint(index) {
    points = points.filter((_, i) => i !== index);
    dispatch('pointsUpdated', points);
  }
</script>

<div class="card w-full bg-base-100 shadow-xl">
  <div class="card-body">
    <h2 class="card-title">{title}</h2>

    <div class="form-control">
      <label class="label">
        <span class="label-text">Paste points (x,y pairs, one per line):</span>
      </label>
      <textarea
        bind:value={pasteArea}
        class="textarea textarea-bordered h-24"
        placeholder="Example:&#10;1,2&#10;3,4&#10;5,6"
      ></textarea>
      <button class="btn btn-secondary mt-2" on:click={handlePaste}>Parse Points</button>
    </div>

    <div class="divider">OR</div>

    <div class="form-control">
      <label class="label">
        <span class="label-text">Enter points manually:</span>
      </label>
      {#each points as point, i}
        <div class="flex gap-2 mb-2">
          <input
            type="number"
            bind:value={point.x}
            on:input={(e) => updatePoint(i, 'x', e.target.value)}
            class="input input-bordered w-full"
            placeholder="x"
          />
          <input
            type="number"
            bind:value={point.y}
            on:input={(e) => updatePoint(i, 'y', e.target.value)}
            class="input input-bordered w-full"
            placeholder="y"
          />
          <button class="btn btn-error" on:click={() => removePoint(i)}>Remove</button>
        </div>
      {/each}
      <button class="btn btn-secondary" on:click={addPoint}>Add Point</button>
    </div>

    <slot {points}></slot>
  </div>
</div>
