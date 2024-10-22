<script>
  let elements = '';
  let percentages = '';
  let result = '';

  function calculateEmpiricalFormula() {
    const elementList = elements.split(',').map(e => e.trim());
    const percentageList = percentages.split(',').map(Number);

    if (elementList.length !== percentageList.length) {
      result = "Error: The number of elements and percentages must match.";
      return;
    }

    const atomicMasses = {
      H: 1.008, C: 12.01, N: 14.01, O: 16.00, // Add more elements as needed
    };

    const moles = percentageList.map((percentage, index) => {
      const element = elementList[index];
      if (!atomicMasses[element]) {
        result = `Error: Atomic mass for ${element} is not available.`;
        return null;
      }
      return percentage / atomicMasses[element];
    });

    if (moles.includes(null)) return;

    const minMoles = Math.min(...moles);
    const ratios = moles.map(mole => Math.round(mole / minMoles));

    result = elementList.map((element, index) => `${element}${ratios[index]}`).join('');
  }
</script>

<div class="card w-full bg-base-100 shadow-xl">
  <div class="card-body">
    <h2 class="card-title">Empirical Formula</h2>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Enter elements (comma separated):</span>
      </label>
      <input type="text" bind:value={elements} class="input input-bordered" placeholder="e.g., C,H,O" />
    </div>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Enter percentages (comma separated):</span>
      </label>
      <input type="text" bind:value={percentages} class="input input-bordered" placeholder="e.g., 40,6.67,53.33" />
    </div>
    
    <div class="card-actions justify-end mt-4">
      <button class="btn btn-primary" on:click={calculateEmpiricalFormula}>Calculate</button>
    </div>
    
    <div class="mt-4">
      <p class="text-lg">Empirical Formula: <span class="font-bold">{result}</span></p>
    </div>
  </div>
</div>
