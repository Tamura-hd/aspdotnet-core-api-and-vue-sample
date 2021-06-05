<template>
  <q-page>
    <div class="row justify-center">
      <div class="col-auto">
        <h4>{{ message }}</h4>
      </div>
    </div>
    <div class="row justify-center">
      <div class="col-auto">
        <q-btn color="primary" label="GET" @click="getData" />
      </div>
    </div>
    <div class="row justify-center q-mt-md">
      <div class="col-auto">
        <q-table
          title="WeatherForecast"
          :columns="columns"
          :data="items"
          class="column-table"
        >
        </q-table>
      </div>
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    message: String,
  },
  data: () => ({
    columns: [
      { name: 'date', label: 'Date', align: 'left', field: 'date', classes: 'bg-cyan-2 ellipsis' },
      { name: 'temperatureC', label: 'TemperatureC', align: 'right', field: 'temperatureC' },
      { name: 'temperatureF', label: 'TemperatureF', align: 'right', field: 'temperatureF' },
      { name: 'summary', label: 'Summary', align: 'left', field: 'summary' },
    ],
    items: [],
  }),

  methods: {
    getData () {
      let self = this;
      this.$axios({
        method: 'get',
        url: '/api/WeatherForecast',
      }).then(function (response) {
        self.items = response.data;
      }).catch(function (error) {
        console.log(error);
      });
    }
  }
}
</script>
