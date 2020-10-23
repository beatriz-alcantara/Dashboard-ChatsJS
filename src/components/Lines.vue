<template>
  <div class="row justify-center">
    <div class="col-8">
      <canvas ref="myCanva" width="100" height="50"></canvas>
    </div>
  </div>
</template>

<script>
import Chart from 'chart.js'

export default {
  props: {
    Data: Array,
    Labels: Array,
    Title: String
  },
  data () {
    return {
      chartLine: {}
    }
  },
  mounted () {
    const canva = this.$refs.myCanva.getContext('2d')
    this.chartLine = new Chart(canva, {
      type: 'line',
      data: {
        labels: this.Labels,
        datasets: [{
          label: this.Title,
          data: this.Data,
          borderWidth: 3,
          fill: false,
          backgroundColor: 'rgba(255, 200, 0, 0.5)',
          borderColor: 'rgba(0, 22, 0, 0.5)'
        }]
      },
      options: {
        scales: {
          yAxes: [{
            ticks: {
              beginAtZero: true
            }
          }]
        }
      }
    })
    this.chartLine.update()
  }
}
</script>

<style>

</style>
