<template>
  <div>
    <div>
    <p>{{ title }}</p>
    <p>{{ pc }}</p> 
    <p class="kom">{{ kom }}</p> 
    <p>{{ choice }}</p>
    </div>
    <ul>
    <p>PC:{{ pcWin }} Player:{{ playerWin}}</p>
    </ul>

    <button @click="rock">Rock</button>
    <button @click="paper">Paper</button>
    <button @click="shears">Shears</button>
  </div>
</template>


<script>
export default {
  data() {
    return{
     title: 'Kamien papier nożyce ',
     counter: '',
     counterPlayer:'',
     choice:"",
     kom:"",
     pc:"",
     pcWin: 0,
     playerWin: 0
    }
}, 
  methods: {
    rock(){
    this.increaseCouner(),
      this.choice="wybrano kamien", this.counterPlayer = 0,
        this.counter === this.counterPlayer ? this.kom = "Remis" : (
        this.counter === 2 ? (this.kom= "wygranko", this.playerWin++):(this.kom = "przgranko", this.pcWin++)
        )
    },
    paper(){
     this.increaseCouner()
      this.choice="wybrano papier", this.counterPlayer = 1,
        this.counter === this.counterPlayer ? this.kom = "Remis" : (
        this.counter === 0 ? (this.kom= "wygranko", this.playerWin++):(this.kom = "przgranko", this.pcWin++)
        )
    },
    shears(){
    this.increaseCouner()
      this.choice="wybrano nozyce", this.counterPlayer = 2,
        this.counter === this.counterPlayer ? this.kom = "Remis" : (
        this.counter === 1 ? (this.kom= "wygranko", this.playerWin++):(this.kom = "przgranko", this.pcWin++)
        )
    },
    increaseCouner(){
      this.counter=Math.floor(Math.random()*3),
        this.counter === 0 ? this.pc="pc wybrał kamien" : null,
        this.counter === 1 ? this.pc="pc wybrał papier" : null,
        this.counter === 2 ? this.pc="pc wybrał nozyce" : null
    },
 }
}
</script>

<style>
  .kom{
     opacity: 0.5;
     color: Red;
  }
</style>