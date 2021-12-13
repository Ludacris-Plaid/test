<template>
 <div id="app">
  {{ info }}
</div> 
</template>
<script>
import axios from "axios";

const options = {
  method: 'GET',
  url: 'https://alpha-vantage.p.rapidapi.com/query',
  params: {
    symbol: 'MSFT',
    function: 'TIME_SERIES_INTRADAY',
    interval: '5min',
    output_size: 'compact',
    datatype: 'json'
  },
  headers: {
    'x-rapidapi-host': 'alpha-vantage.p.rapidapi.com',
    'x-rapidapi-key': '2c601b3b32msh064b8868b8ec3fap1503e7jsn7220e561b8c8'
  }
};

axios.request(options).then(function (response) {
	console.log(response.data);
}).catch(function (error) {
	console.error(error);
});
</script>

<style scoped>

</style>