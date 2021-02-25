<template>
  <!-- <h2 v-once>{{name}}</h2>
  <button @click="name = 'Batman'">Change name</button>
  <h2 v-pre>{{name}}</h2> -->
  <h2>Fullname - {{ firstname }} {{ lastname }}</h2>
  <h2>Computed fullname - {{ fullName }}</h2>

<button @click="changeFullName">Change fullname</button>

  <button @click = "items.push({id: 4, title: 'keyboard', price: 50})" >Add item</button>
  <h2>Computed total - {{ total }} </h2>
  <input type="text" v-model="country">
  <h2>Method Total - {{ getTotal() }} </h2>

  <template v-for="item in items" :key="item.id">
    <h2 v-if="item.price > 100">{{ item.title }} {{ item.price }} </h2>
  </template>

  <h2 v-for="item in expensiveItems" :key="item.id">{{ item.title }} {{ item.price }} </h2>

</template>

<script>
  export default {
    name: 'App',
    data(){
      return {
        firstname: "Bruce",
        lastname: "Wayne",
        items: [
          {
            id: 1,
            title: 'TV',
            price: 100,
          },
          {
            id: 2,
            title: 'Phone',
            price: 200,
          },
          {
            id: 3,
            title: 'Laptop',
            price: 500
          },
        ],
        country: ''
      }
    },
    methods: {
      
      getTotal() {
        console.log('getTotal Method')
         return this.items.reduce((total, curr) => (total = total + curr.price), 0)
      },
      changeFullName(){
        this.fullName = 'Clark Kent'
      }
    },
    computed: {
      fullName: {        
        get() {
          return `${this.firstname} ${this.lastname}`
        },
        set(value) {
          const names = value.split(' ')
          this.firstname = names[0]
          this.lastname = names[1]
        }     
         
      },
      total(){
        console.log('total computed property')
        return this.items.reduce((total, curr) => (total = total + curr.price), 0)
      },
      expensiveItems() {
        return this.items.filter( item => item.price > 100 )
      }
    }
  }
</script>

<style>

</style>
