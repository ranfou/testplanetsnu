<template>
  
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
        <tr>
            <td>The table body</td>
            <td>with two columns</td>
            <td>The table body</td>
            <td>with two columns</td>
            <td>The table body</td>
        </tr>
    </tbody>
</table>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
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
