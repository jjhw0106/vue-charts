<template>
  <div>
    <h1>BarChart</h1>
    <Bar :data="chartData" :options="chartOptions" />
    <canvas></canvas>
  </div>
</template>

<script>
import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale
} from 'chart.js'

import {Bar} from 'vue-chartjs'

ChartJS.register(CategoryScale, LinearScale, BarElement, Title, Tooltip, Legend)

export default {
  name: 'App',
  components: {
    Bar
  },
  data() {
    return {
      chartData: {
        labels: [],
        datasets: [{  }],
      },
      chartOptions: {
        responsive: true,
        maintainAspectRatio: true
      }
    }
  },
  mounted() {
    this.chartData = {
      labels: ['January', 'February', 'March'],
      datasets: [{ data: [90, 20, 12] }],
    }
  }
}
</script>

<style>

</style>