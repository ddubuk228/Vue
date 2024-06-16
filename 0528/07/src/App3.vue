<template>
  <div>
    <h2>관심 있는 K-POP 가수는?</h2>
    <hr />
    <ul>
      <CheckBoxItem v-for="idol in idols" :idol="idol" />
    </ul>
  </div>
</template>

<script>
  import CheckBoxItem from './components/CheckBoxItem3.vue'
  import Idol from './idol'
  export default {
    name:"App3",
    components: {CheckBoxItem},
    data(){
      return{
        idols:[
          new Idol(1, "NewJeans", true),
          new Idol(2, "IVE", false),
          new Idol(3, "Aespa", false),
          new Idol(4, "(G)-IDLE", false),
        ]
      }
    },
  }
</script>

<style scoped>

</style>