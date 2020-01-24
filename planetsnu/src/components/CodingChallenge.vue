<template>
  <div id='app'>
  <table>
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
        <tr v-for="game in games" :key="game.name">
            <td>{{ game.name }}</td>
            <td>{{ game.shortdescription }}</td>
            <td>{{ game.datecreated }}</td>
            <td>{{ game.createdby }}</td>
            <td>{{ game.hostdays }}</td>
            <td>{{ game.password }}</td>
        </tr>
    </tbody>
</table>
</div>
</template>

<script>
export default {
  el: '#app',
  name: 'CodingChallenge',
  props: {
    
  },
  data(){
    return {
      games: [],
    }
  },
  mounted(){
    const baseURI = 'http://api.planets.nu/games/list?status=1'
      this.$http.get(baseURI)
      .then((result) => {
        this.games = result.data
      })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
table, td{
  border-collapse: collapse;
  border-spacing: 0;
  border: 1px solid #ddd;
}
tr:nth-child(even) {
  background-color: #f2f2f2;
}
th, td {
  text-align: left;
  padding: 16px;
}
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
