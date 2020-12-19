<template>
  <div>
    <ul>
      <li v-for="run in runs" v-bind:key="run.id">{{run}}</li>
    </ul>
  </div>
</template>

<script>
  import axios from 'axios'

export default {
  name: "Dashboard",
  data() {
    return {
      runs: null
    };
  },
  mounted() {
    axios.get("http://localhost:8000/api/heroad/run/").then(response  => {
      this.runs = response.data
      console.log(response)
    });
  }
};
</script>

<style scoped></style>
