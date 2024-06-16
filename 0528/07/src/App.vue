<template>
  <div>
    <h2>관심 있는 K-POP 가수는?</h2>
    <hr />
    <ul>
      <CheckBoxItem v-for="idol in idols" :key="idol.id"
        :id="idol.id" :name="idol.name" :checked="idol.checked" />
    </ul>
  </div>
</template>

<script>
  import CheckBoxItem from './components/CheckBoxItem.vue'
  export default {
    name:"App",
    components: {CheckBoxItem},
    data(){
      return{
        idols:[
          {id:1, name:"NewJeans"},
          {id:2, name:"IVE"},
          {id:3, name:"Aespa"},
          {id:4, name:"(G)-IDLE"}
        ]
      }
    },
  }
</script>

<style scoped>

</style>