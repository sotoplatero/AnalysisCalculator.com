<script>
  import { createEventDispatcher } from 'svelte';
  
  let numbers = '';
  let q1 = 0;
  let q2 = 0;
  let q3 = 0;
  
  function calculateQuartiles() {
    const values = numbers.split(/[,\s]+/).map(Number).filter(n => !isNaN(n)).sort((a, b) => a - b);
    
    if (values.length < 4) {
      alert('Please enter at least 4 numbers to calculate quartiles.');
      return;
    }
    
    const n = values.length;
    
    // Calculate Q2 (median)
    q2 = n % 2 === 0
      ? (values[n/2 - 1] + values[n/2]) / 2
      : values[Math.floor(n/2)];
    
    // Calculate Q1
    const lowerHalf = values.slice(0, Math.floor(n/2));
    q1 = lowerHalf.length % 2 === 0
      ? (lowerHalf[lowerHalf.length/2 - 1] + lowerHalf[lowerHalf.length/2]) / 2
      : lowerHalf[Math.floor(lowerHalf.length/2)];
    
    // Calculate Q3
    const upperHalf = n % 2 === 0 ? values.slice(n/2) : values.slice(Math.floor(n/2) + 1);
    q3 = upperHalf.length % 2 === 0
      ? (upperHalf[upperHalf.length/2 - 1] + upperHalf[upperHalf.length/2]) / 2
      : upperHalf[Math.floor(upperHalf.length/2)];
  }
</script>

<div class="card w-full bg-base-100 shadow-xl">
  <div class="card-body">
    <h2 class="card-title">Quartile Calculator</h2>
    
    <div class="form-control">
      <label class="label">
        <span class="label-text">Enter numbers (comma or space separated):</span>
      </label>
      <textarea
        bind:value={numbers}
        class="textarea textarea-bordered h-24"
        placeholder="Example: 1, 2, 3, 4, 5, 6, 7, 8, 9, 10"
      ></textarea>
    </div>
    
    <div class="card-actions justify-end mt-4">
      <button class="btn btn-primary" on:click={calculateQuartiles}>Calculate Quartiles</button>
    </div>
    
    <div class="mt-4">
      <p class="text-lg">Q1 (First Quartile): <span class="font-bold">{q1}</span></p>
      <p class="text-lg">Q2 (Median): <span class="font-bold">{q2}</span></p>
      <p class="text-lg">Q3 (Third Quartile): <span class="font-bold">{q3}</span></p>
    </div>
  </div>
</div>
