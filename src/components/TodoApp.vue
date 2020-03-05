<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
     <StoneAndPaper />
    <div class="item">
     <p>Nowe todo: {{newItem}}</p>
      <input type="text" placeholder="" v-model="newItem">
      <button @click="addItem">Dodaj</button>

     
       <TodoItem 
        v-for="item in items"
        :key="item.id"
        :item="item"
        @removeClicked="removeItem"
        />

    </div> 
    
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue'
import StoneAndPaper from './StoneAndPaper.vue'

export default {
 components:{
     TodoItem,
     StoneAndPaper
 },
  data() {
    return{
     title: 'klik klik',
     counter: 0,
     newItem: '', 
     items: [
       { title: 'Zad 1', completed: false, id: 1 },
       { title: 'Zad 2', completed: false, id: 2 }
     ]
    }
  },
  methods: {
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
body {
  background-color: #fff;
}
.completed {
  opacity: 0.5;
}
.completed h2 {
  text-decoration: line-through;
}

</style>
