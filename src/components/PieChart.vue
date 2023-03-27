<template>
  <div id="chart">
    <!-- <h1>Piechart</h1> -->
    <vue-apex-charts
      type="pie"
      width="380"
      :options="chartOptions"
      :series="series"
    ></vue-apex-charts>
  </div>
</template>

<script>
import VueApexCharts from "vue-apexcharts";

export default {
  name: "PieChart",
  data: () => ({
    series: [],
  }),
  props: {
    checkins: {
      type: Array,
      default() {
        return [];
      },
    },
    users: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  computed: {
    chartOptions() {
      let values = [];
      let users = this.users.map((v, i) => {
        values[i] = v.checkins.length;
        return v.full_name;
      });
      this.series = [25, 15, 44, 55, 41, 17];

      return {
        theme: {
          monochrome: {
            enabled: true,
          },
        },
        chart: {
          width: 380,
          type: "pie",
        },
        labels:["Team A", "Team B", "Team C", "Team D", "Team E"],
        responsive: [
          {
            breakpoint: 480,
            options: {
              chart: {
                width: 200,
              },
              legend: {
                position: "right", 
              },
            },
          },
        ],
      };
    },
  },
  components: {
    VueApexCharts,
  },
};
</script>
<style >
span.apexcharts-legend-text{
  color: grey !important;
}
</style>
