<script>
export default {
  name: 'App',
  data() {
    return {
      emailsArr: []
    }
  },
  mounted() {

    for (let i = 0; i < 10; i++) {
      axios.get('https://flynn.boolean.careers/exercises/api/random/mail')
        .then((response) => {
          let email = response.data.response

          this.emailsArr.push(email)

        })
    }

  }
}
</script>
<template>
  <h1>Generated Emails</h1>

  <ul v-for="email in emailsArr">
    <li>{{ email }}</li>
  </ul>
</template>


<style>
body {
  font-family: Arial, Helvetica, sans-serif;
  background-color: #ededed;
}

h1,
ul {
  text-align: center;
  list-style: none;
}
</style>