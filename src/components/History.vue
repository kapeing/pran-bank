<template>
  <section class="container">
    <h1>{{ title }}</h1>
    <p>{{ message }}</p>
    <table>
      <tr>
        <th>User ID</th>
        <td>{{ userData.userId }}</td>
      </tr>
      <tr>
        <th>ID</th>
        <td>{{ userData.id }}</td>
      </tr>
      <tr>
        <th>Title</th>
        <td>{{ userData.title }}</td>
      </tr>
      <tr>
        <th>Body</th>
        <td>{{ userData.body }}</td>
      </tr>
    </table>
  </section>
</template>

<script>
const axios = require('axios')

let url = 'https://jsonplaceholder.typicode.com/posts/'

export default {
  data: function () {
    return {
      title: 'Axios',
      msg: '',
      message: 'axios sample.',
      userData: {}
    }
  },
  mounted: function () {
    this.getUserData()
  },
  methods: {
    async getUserData () {
      let id = 1 // ●id番号
      let result = await axios.get(url + id)
      console.log(result.data)
      this.userData = result.data
    }
  }
}
</script>

<style>
.container {
  padding: 5px 10px;
}
h1 {
  font-size: 60pt;
  color: #345980;
}
p {
  padding-top:5px;
  font-size: 20pt;
}
div {
    font-size:14pt;
}
pre {
  padding: 10px;
  font-size: 18pt;
  background-color: #efefef;
  white-space: pre-wrap ;
}
hr {
  margin:10px 0px;
}
</style>
