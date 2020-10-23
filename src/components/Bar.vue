<template>
  <div class="row justify-center">
    <div class="col-8">
      <canvas id="myChart" width="100" height="50"></canvas>
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
      form: {
        label: '',
        data: ''
      },
      data: {
        labels: [],
        datasets: [{
          label: '',
          data: [],
          backgroundColor: [
            'rgba(255, 99, 132, 0.2)',
            'rgba(54, 162, 235, 0.2)',
            'rgba(255, 206, 86, 0.2)',
            'rgba(75, 192, 192, 0.2)',
            'rgba(153, 102, 255, 0.2)',
            'rgba(255, 159, 64, 0.2)'
          ],
          borderColor: [
            'rgba(255, 99, 132, 1)',
            'rgba(54, 162, 235, 1)',
            'rgba(255, 206, 86, 1)',
            'rgba(75, 192, 192, 1)',
            'rgba(153, 102, 255, 1)',
            'rgba(255, 159, 64, 1)'
          ],
          borderWidth: 1
        }]
      },
      myChart: {}
    }
  },
  mounted () {
    var ctx = document.getElementById('myChart').getContext('2d')
    this.myChart = new Chart(ctx, {
      type: 'bar',
      data: this.data,
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
    this.setVariables()
  },
  methods: {
    setVariables () {
      this.data.datasets[0].label = this.Title
      this.data.datasets[0].data = this.Data
      this.data.labels = this.Labels
      this.myChart.update()
    },
    adicionar () {
      this.data.labels.push(this.form.label)
      this.data.datasets[0].data.push(this.form.data)
      this.myChart.update()
    }
  }
}
</script>

<style>

</style>
