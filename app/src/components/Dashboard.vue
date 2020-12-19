<template>
  <div>{{runs}}</div>
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
      this.runs = response
      console.log(response)
    });
  }
};
</script>

<style scoped></style>
