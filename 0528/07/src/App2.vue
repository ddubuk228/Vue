<template>
  <div>
    <h2>관심 있는 K-POP 가수는?</h2>
    <hr />
    <ul>
      <CheckBoxItem v-for="idol in idols" :key="idol.id"
        :idol="idol" />
    </ul>
  </div>
</template>

<script>
  import CheckBoxItem from './components/CheckBoxItem2.vue'
  export default {
    name:"App",
    components: {CheckBoxItem},
    data(){
      return{
        idols:[
          {id:1, name:"NewJeans", checked:false},
          {id:1, name:"IVE", checked:false},
          {id:1, name:"Aespa", checked:false},
          {id:1, name:"(G)-IDLE", checked:false}
        ]
      }
    },
  }
</script>

<style scoped>

</style>