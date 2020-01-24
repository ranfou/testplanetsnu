<template>
  <div id='app'>
  <table border="1">
    <thead>
        <tr>
            <th>Name</th>
        
            <th>Short Description</th>
        
            <th>Date Created</th>
        
            <th>Created By</th>
        
            <th>Host Days</th>
       
            <th>Password</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>The table body</td>
            <td>with two columns</td>
            <td>The table body</td>
            <td>with two columns</td>
            <td>The table body</td>
        </tr>
    </tbody>
</table>

    {{ games }}  

<button v-on:click="fetchUsers">FetchGames</button>
</div>
</template>

<script>
export default {
  el: '#app',
  name: 'CodingChallenge',
  props: {
    msg: String
  },
  data(){
    return {
      games: [],
    }
  },
  methods: {
    fetchUsers: function () {
      const baseURI = 'http://api.planets.nu/games/list'
      this.$http.get(baseURI)
      .then((result) => {
        this.games = result.data
      })
    }
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
