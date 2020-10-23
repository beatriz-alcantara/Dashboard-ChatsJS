<template>
  <q-page class="row justify-center">
    <div class="row col-12">
      <div class="col-6">
        <bar :Data="[12, 19, 3, 5, 2, 3]" :Labels="['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'] " Title="Meu gráfico"/>
      </div>
      <div class="col-6">
        <lines :Data="[12, 19, 3, 5, 2, 3]" :Labels="['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'] " Title="Gráfico de linha"/>
      </div>
      <div class="col-6">
        <radar :Data="[12, 19, 20, 5, 2, 3]" :Labels="['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'] " Title="Radar"/>
      </div>
      <div class="col-6">
        <pie :Data="[12, 19, 20, 5, 2, 3]" :Labels="['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'] " Title="Pie"/>
      </div>
      <div class="col-6">
        <doughnut :Data="[12, 19, 20, 5, 2, 3]" :Labels="['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'] " Title="Doughnut"/>
      </div>
      <div class="col-6">
        <polar-area :Data="[12, 19, 20, 5, 2, 3]" :Labels="['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'] " Title="Polar Area"/>
      </div>
      <div class="col-6">
        <bubbles :Data="dataBubble" :Labels="['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'] " Title="Bubble"/>
      </div>
      <div class="col-6">
        <scatter :Data="[{ x: 5, y: 3 }, { x: 8, y: 5 }, { x: -10, y: 2 }, { x: 2, y: 3 }, { x: 1, y: 10 }]" :Labels="['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'] " Title="Bubble"/>
      </div>
      <div class="col-6">
        <mixed :Data="[{ x: 5, y: 3 }, { x: 8, y: 5 }, { x: -10, y: 2 }, { x: 2, y: 3 }, { x: 1, y: 10 }]" :Labels="['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'] " Title1="Bar" Title2="Line"/>
      </div>
    </div>
  </q-page>
</template>

<script>
import Bar from 'components/Bar'
import Lines from 'components/Lines'
import Radar from 'components/Radar'
import Pie from 'components/Pie'
import Doughnut from 'components/Doughnut'
import PolarArea from 'components/PolarArea'
import Bubbles from 'components/Bubbles'
import Scatter from 'components/Scatter'
import Mixed from 'components/Mixed'

export default {
  components: {
    Bar,
    Lines,
    Radar,
    Pie,
    Doughnut,
    PolarArea,
    Bubbles,
    Scatter,
    Mixed
  },
  data () {
    return {
      dataBubble: [
        { x: 5, y: 3, r: 15 },
        { x: 7, y: 4, r: 15 },
        { x: 8, y: 3, r: 15 },
        { x: 9, y: 6, r: 15 },
        { x: 7, y: 3, r: 15 },
        { x: 7, y: 3, r: 15 },
        { x: 12, y: 7, r: 15 },
        { x: 13, y: 4, r: 15 }
      ]
    }
  }
}
</script>

<style>

</style>
