<template>

  <div class="grid md:grid-cols-2 gap-4">
    <!-- Box 1 -->
    <iframe src="https://datahub.io/core/covid-19/view/1" width="100%" height="520px" frameborder="0"></iframe>
    <div class="shadow-md bg-yellow-400 p-4 text-center rounded">
      <h5 class="text-1xl text-grey-70 font-bold mb-1">RECENTS CASES</h5>

      <div class="text-2xl mb-4">
        <span class="font-bold">Newest:</span>
        {{ numberWithCommas(stats.NewConfirmed) }}
      </div>
      <div class="text-3xl mb-4">
        <span class="font-bold">Total:</span>
        {{ numberWithCommas(stats.TotalConfirmed) }}
      </div>
    </div>
    <!-- Box 2 -->
    <div class="shadow-md bg-red-500 p-1 text-center rounded">
      <h3 class="text-1xl text-blue-200 font-bold mb-10">RECENTS DEATHS TOLLS</h3>

      <div class="text-2xl mb-4">
        <span class="font-bold">DEATH RATES</span>
        {{ numberWithCommas(stats.NewDeaths) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total:</span>
        {{ numberWithCommas(stats.TotalDeaths) }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DataBoxes',
  props: ['stats'],
  setup () {
    return {
      numberWithCommas (x) {
        return x.toString()
          .replace(/\B(?=(\d{3})+(?!\d))/g, ',');
      }
    };
  }
};
</script>
