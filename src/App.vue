<template>
  <div id="app">
   <table>
      <thead>
        <tr>
        <th>Title</th>
        <th>Price</th>
        <th>Quantity</th>
        <th>Operations</th>
        <th>Összérték</th>
      </tr>
      </thead>
      <tbody>
        <tr v-for="row in rows"
            v-bind:key="row.title"
            v-on:delete-item="deleteRow">
            <td>{{row.title}}</td>
            <td>{{row.price}}</td>
            <td>{{row.quantity}}</td>
            <td>
              <button>X</button>
              <button>Edit</button>
            </td>
            <td>{{row.price * row.quantity}}</td>
        </tr>
        <tr v-for="row in rows"
            v-bind:key="row.title">
            <td></td>
        </tr>
        
      </tbody>
    </table>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      rows: [
        {
          title: 'Kerék',
          price: 100,
          quantity: 12
        },
        {
          title: 'Teleszkóp',
          price: 1000,
          quantity: 300
        },
        {
          title: 'Kormány',
          price: 230,
          quantity: 5
        },
        {
          title: 'Ajtó',
          price: 45120,
          quantity: 321
        },
      ]
    }
  },
   methods: {
    deleteRow(rows){
      this.rows = this.rows.filter(function(item){
        return rows.title != item.title
      })
    }
  } 
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
