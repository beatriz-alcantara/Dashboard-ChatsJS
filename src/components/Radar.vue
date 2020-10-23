<template>
  <div class="row justify-center">
    <div class="col-8">
      <canvas ref="myCanva"></canvas>
    </div>
  </div>
</template>

<script>
import Chart from 'chart.js'
export default {
  props: {
    Data: Array,
    Title: String,
    Labels: Array
  },
  data () {
    return {
      myChart: {}
    }
  },
  mounted () {
    const canva = this.$refs.myCanva.getContext('2d')
    this.myChart = new Chart(canva, {
      type: 'radar',
      data: {
        labels: this.Labels,
        datasets: [{
          label: this.Title,
          data: this.Data,
          borderColor: 'rgba(245, 66, 224, 0.5)'
        }]
      }
    })
  }
}
</script>

<style>

</style>
