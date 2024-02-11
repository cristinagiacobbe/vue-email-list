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
    <li v-for="mail in list">{{ mail }}</li>

  </ul>
</template>

<style scoped></style>
