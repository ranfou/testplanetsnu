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
        <tr v-on:click="visitGame(game.id)" v-for="game in games" :key="game.name">
            <td>{{ game.name }}</td>
            <td>{{ game.shortdescription }}</td>
            <td>{{ game.datecreated }}</td>
            <td>{{ game.createdby }}</td>
            <td>{{ game.hostdays }}</td>
            <td>{{ game.password }}</td> <!-- check game.haspassword for ternary to show lock icon -->
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
      id: null
    }
  },
  methods: {
    visitGame: function (){

      //example game
      window.open("https://planets.nu/#/sector/353518", "_blank");
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
table {
  border-spacing: 1;
  border: 1px solid grey;
}
tr:nth-child(odd) {
  background-color: #f2f2f2;
}
th {
  background-color:white;
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
