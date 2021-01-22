<template>
  <div class="container">
    <div class="row my-5">
      <button class="btn btn-primary btn-sm" @click="updateChart">
        Actualizar gráfica
      </button>
    </div>

    <div class="row">
      <div class="col-md-4">
        <apexchart
          height="300"
          type="line"
          :options="options"
          :series="series"
        ></apexchart>
      </div>
      <div class="col-md-4">
        <apexchart
          height="300"
          type="bar"
          :options="options"
          :series="series"
        ></apexchart>
      </div>
      <div class="col-md-4">
        <apexchart
          height="300"
          type="area"
          :options="options"
          :series="series"
        ></apexchart>
      </div>
      <div class="col-md-4">
        <apexchart
          height="300"
          type="donut"
          :options="optionsDos"
          :series="seriesDos"
        ></apexchart>
      </div>
      <div class="col-md-8">
        <apexchart
          height="300"
          type="bar"
          :options="options"
          :series="series"
        ></apexchart>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "App",
      // Datos de la gráfica No: 1
      options: {
        chart: {
          id: "vuechart-example",
        },
        xaxis: {
          categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998],
        },
      },
      series: [
        {
          name: "series-1",
          data: [30, 40, 45, 50, 49, 60, 70, 91],
        },
      ],

      // Datos de la gráfica No: 2

      optionsDos: {
        chart: {
          type: "donut",
        },
        labels: ["Apple", "Mango", "Orange", "Watermelon"],
      },

      seriesDos: [44, 55, 13, 33],
    };
  },
  mounted: function () {},
  methods: {
    updateChart: function () {
      this.options = {
        xaxis: {
          categories: [2000, 2001, 2002, 2003, 2004, 2005],
        },
      };

      this.series = [
        {
          data: [10, 20, 30, 40, 20, 90],
        },
      ];

      this.optionsDos = {
        labels: ["Manzana", "Mango", "Naranja", "Sandia"],
      };
      this.seriesDos = [10, 90, 2, 5];
    },
  },
};
</script>


