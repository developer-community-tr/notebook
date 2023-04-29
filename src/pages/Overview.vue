<template>
  <div class="content">
    <div class="container-fluid">
      <div class="row">
        <div class="col-xl-3 col-md-6">
          <stats-card>
            <div slot="header" class="icon-warning">
              <i class="nc-icon nc-chart text-warning"></i>
            </div>
            <div slot="content">
              <p class="card-category">Word Count</p>
              <h4 class="card-title">
                {{ getWordsCount }}
              </h4>
            </div>
            <div slot="footer">
              <i class="fa fa-refresh"></i>They are new for me
            </div>
          </stats-card>
        </div>

        <div class="col-xl-3 col-md-6">
          <stats-card>
            <div slot="header" class="icon-success">
              <i class="nc-icon nc-light-3 text-success"></i>
            </div>
            <div slot="content">
              <p class="card-category">Phrases</p>
              <h4 class="card-title">415</h4>
            </div>
            <div slot="footer">
              <i class="fa fa-calendar-o"></i>Helps to understand how I use
            </div>
          </stats-card>
        </div>

        <div class="col-xl-3 col-md-6">
          <stats-card>
            <div slot="header" class="icon-danger">
              <i class="nc-icon nc-vector text-danger"></i>
            </div>
            <div slot="content">
              <p class="card-category">Idioms</p>
              <h4 class="card-title">23</h4>
            </div>
            <div slot="footer">
              <i class="fa fa-clock-o"></i>Funny and clever
            </div>
          </stats-card>
        </div>

        <div class="col-xl-3 col-md-6">
          <stats-card>
            <div slot="header" class="icon-info">
              <i class="nc-icon nc-favourite-28 text-primary"></i>
            </div>
            <div slot="content">
              <p class="card-category">Examples</p>
              <h4 class="card-title">+45</h4>
            </div>
            <div slot="footer">
              <i class="fa fa-refresh"></i>Memorise it
            </div>
          </stats-card>
        </div>

      </div>
      <div class="row">
        <div class="col-md-6">
          <chart-card :chart-data="barChartDefaults.data" :chart-options="barChartDefaults.options"
            :chart-responsive-options="barChartDefaults.responsiveOptions" chart-type="Bar">
            <template slot="header">
              <h4 class="card-title">Word Levels</h4>
              <p class="card-category">Count comparsation of word levels and origins</p>
            </template>
            <template slot="footer">
              <div class="legend">
                <i class="fa fa-circle text-info"></i> English
                <i class="fa fa-circle text-danger"></i> Danish
                <i class="fa fa-circle text-warning"></i> French
              </div>
              <hr>
              <div class="stats">
                <i class="fa fa-check"></i> Data information certified from internet
              </div>
            </template>
          </chart-card>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import ChartCard from 'src/components/Cards/ChartCard.vue'
import StatsCard from 'src/components/Cards/StatsCard.vue'
import StaticData from 'src/components/Data/StaticData.vue'

export default {
  components: {
    ChartCard,
    StatsCard,
    StaticData
  },
  created() {
    this.words = StaticData.words;
  },
  data() {
    return {
      words: null,
      barChartDefaults: {
        data: {
          labels: ['A1', 'A2', 'B1', 'B2', 'C1', 'C2', 'unknown'],
          series: [
            [34, 12, 21, 40, 56, 4, 0],
            [5, 12, 43, 40, 56, 4, 5],
            [34, 52, 21, 34, 21, 14, 2]
          ]
        },
        options: {
          seriesBarDistance: 10,
          axisX: {
            showGrid: false
          },
          height: '245px'
        },
        responsiveOptions: [
          ['screen and (max-width: 640px)', {
            seriesBarDistance: 5,
            axisX: {
              labelInterpolationFnc(value) {
                return value[0]
              }
            }
          }]
        ]
      }
    }
  },
  computed: {
    getWordsCount() {
      return this.words.length;
    }
  }
}
</script>
<style>

</style>
