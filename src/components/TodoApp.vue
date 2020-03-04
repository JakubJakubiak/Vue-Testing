<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <p>{{ title }}</p>
    <p>{{ counter}}</p>
    <button @click="increaseCouner">1++</button>
    <div class="item">
     <p>Nowe todo: {{newItem}}</p>
      <input type="text" placeholder="" v-model="newItem">
      <button @click="addItem">Dodaj</button>
    </div> 

       <TodoItem 
        v-for="item in items"
        :key="item.id"
        :item="item"
        @removeClicked="removeItem"
        />


  </div>
</template>

<script>
import TodoItem from './TodoItem.vue'

export default {
 components:{
     TodoItem
 },
  data() {
    return{
     title: 'klik klik',
     counter: 0,
     newItem: '', 
     items: [
       { title: 'Klik ', completed: false, id: 1 },
       { title: 'Klik 2', completed: false, id: 2 }
     ]
    }
  },
  methods: {
  increaseCouner(){
   this.counter++
   },
    addItem() {
      this.items.push({
         title: this.newItem,
         completed: false,
         id: Math.random()
         })
      this.newItem = ''
    },
    removeItem(id) {
      const index = this.items.findIndex(el => el.id === id)
      this.items[index].completed = true
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
.item{

}
.completed {
  opacity: 0.5;
}
.completed h2 {
  text-decoration: line-through;
}

</style>
