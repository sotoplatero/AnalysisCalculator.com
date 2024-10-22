<script>
  import { base } from '$app/paths';
</script>

<div class="container mx-auto p-4">
  <h1 class="text-3xl font-bold mb-4">Calculators</h1>

  <p class="mb-4">Choose the type of calculation you want to perform:</p>

  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">Linear Interpolation</h2>
        <p>Calculate linear interpolation between two points.</p>
        <div class="card-actions justify-end">
          <a href="{base}/interpolation/linear" class="btn btn-primary">Go to Calculator</a>
        </div>
      </div>
    </div>

    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">Cubic Interpolation</h2>
        <p>Perform cubic interpolation for smooth curves.</p>
        <div class="card-actions justify-end">
          <a href="{base}/interpolation/cubic" class="btn btn-primary">Go to Calculator</a>
        </div>
      </div>
    </div>

    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">Polynomial Interpolation</h2>
        <p>Calculate polynomial interpolation for multiple points.</p>
        <div class="card-actions justify-end">
          <a href="{base}/interpolation/polynomial" class="btn btn-primary">Go to Calculator</a>
        </div>
      </div>
    </div>

    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">Lagrange Interpolation</h2>
        <p>Use Lagrange polynomials for interpolation.</p>
        <div class="card-actions justify-end">
          <a href="{base}/interpolation/lagrange" class="btn btn-primary">Go to Calculator</a>
        </div>
      </div>
    </div>

    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">Quartile Calculator</h2>
        <p>Calculate quartiles for a set of numbers.</p>
        <div class="card-actions justify-end">
          <a href="{base}/calculator/quartile" class="btn btn-primary">Go to Calculator</a>
        </div>
      </div>
    </div>

    <!-- New calculators -->
    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">Expected Value</h2>
        <p>Calculate the expected value of a discrete random variable.</p>
        <div class="card-actions justify-end">
          <a href="{base}/calculator/expected-value" class="btn btn-primary">Go to Calculator</a>
        </div>
      </div>
    </div>

    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">Inverse Laplace Transform Calculator</h2>
        <p>Calculate the inverse Laplace transform of a function.</p>
        <div class="card-actions justify-end">
          <a href="{base}/calculator/inverse-laplace" class="btn btn-primary">Go to Calculator</a>
        </div>
      </div>
    </div>

    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">Polynomial Long Division Calculator</h2>
        <p>Perform long division of polynomials.</p>
        <div class="card-actions justify-end">
          <a href="{base}/calculator/polynomial-long-division" class="btn btn-primary">Go to Calculator</a>
        </div>
      </div>
    </div>

    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">Frequency Calculator</h2>
        <p>Calculate the frequency of items in a dataset.</p>
        <div class="card-actions justify-end">
          <a href="{base}/calculator/frequency" class="btn btn-primary">Go to Calculator</a>
        </div>
      </div>
    </div>

    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">Poisson Distribution Calculator</h2>
        <p>Calculate probabilities using the Poisson distribution.</p>
        <div class="card-actions justify-end">
          <a href="{base}/calculator/poisson-distribution" class="btn btn-primary">Go to Calculator</a>
        </div>
      </div>
    </div>

    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">Mean Absolute Deviation Calculator</h2>
        <p>Calculate the mean absolute deviation of a dataset.</p>
        <div class="card-actions justify-end">
          <a href="{base}/calculator/mean-absolute-deviation" class="btn btn-primary">Go to Calculator</a>
        </div>
      </div>
    </div>

    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">Outlier</h2>
        <p>Identify outliers in a dataset.</p>
        <div class="card-actions justify-end">
          <a href="{base}/calculator/outlier" class="btn btn-primary">Go to Calculator</a>
        </div>
      </div>
    </div>

    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">Relative Frequency</h2>
        <p>Calculate relative frequencies of items in a dataset.</p>
        <div class="card-actions justify-end">
          <a href="{base}/calculator/relative-frequency" class="btn btn-primary">Go to Calculator</a>
        </div>
      </div>
    </div>

    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">Simpson's Rule</h2>
        <p>Approximate definite integrals using Simpson's rule.</p>
        <div class="card-actions justify-end">
          <a href="{base}/calculator/simpsons-rule" class="btn btn-primary">Go to Calculator</a>
        </div>
      </div>
    </div>

    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">Critical Number</h2>
        <p>Find critical numbers of a function.</p>
        <div class="card-actions justify-end">
          <a href="{base}/calculator/critical-number" class="btn btn-primary">Go to Calculator</a>
        </div>
      </div>
    </div>

    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">Five Number Summary</h2>
        <p>Calculate the five-number summary of a dataset.</p>
        <div class="card-actions justify-end">
          <a href="{base}/calculator/five-number-summary" class="btn btn-primary">Go to Calculator</a>
        </div>
      </div>
    </div>

    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">Empirical Formula</h2>
        <p>Calculate the empirical formula of a compound.</p>
        <div class="card-actions justify-end">
          <a href="{base}/calculator/empirical-formula" class="btn btn-primary">Go to Calculator</a>
        </div>
      </div>
    </div>

    <div class="card bg-base-100 shadow-xl">
      <div class="card-body">
        <h2 class="card-title">Euler's Method</h2>
        <p>Solve differential equations using Euler's method.</p>
        <div class="card-actions justify-end">
          <a href="{base}/calculator/eulers-method" class="btn btn-primary">Go to Calculator</a>
        </div>
      </div>
    </div>
  </div>
</div>
