<script >
import axios from 'axios'

export default {
  name: 'App',
  data() {
    return {
      base_api_url: "https://flynn.boolean.careers/exercises/api/random/mail",
      list: []
    }
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/random/mail")
      .then((response) => {
        console.log(response.data.response);
        this.list.push(response.data.response);
        console.log(this.list);
      })

    for (let i = 0; i < 10; i++) {
      axios
        .get("https://flynn.boolean.careers/exercises/api/random/mail")
        .then((response) => {
          this.list.push(response.data.response);
          console.log(this.list);
        })

    }
  }
}

</script>

<template>
  <ul>
    <li>{{ list[0] }}</li>
    <li>{{ list[1] }}</li>
    <li>{{ list[2] }}</li>
    <li>{{ list[3] }}</li>
    <li>{{ list[4] }}</li>
    <li>{{ list[5] }}</li>
    <li>{{ list[6] }}</li>
    <li>{{ list[7] }}</li>
    <li>{{ list[9] }}</li>
    <li>{{ list[10] }}</li>
  </ul>
</template>

<style scoped></style>
