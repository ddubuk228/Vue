<template>
  <div>
    <h2>최신 인기곡</h2>
    <SongList :songs="songs" />
  </div>
  <br /><br />
  <button @click="changedModal">Teleport를 이용한 Modal 기능</button>
  <teleport to="#modal">
    <Modal v-if="isModal" />
  </teleport>
</template>

<script>
  import { computed } from 'vue'
  import SongList from './components/SongList.vue'
  import Modal from './components/Modal.vue'

  export default {
    name: "App",
    components: { SongList, Modal },
    data() {
      return {
        songs: [
          { id:1, title:"잘 지내자, 우리", done:true },
          { id:2, title:"그때는 아니었다", done:true },
          { id:3, title:"섬 같은 곳으로", done:false},
          { id:4, title:"지나가요", done:false },
        ],
        isModal: false,
      }
    },
    methods:{
      changedModal() {
        this.isModal = true;
        setTimeout(()=> { this.isModal = false }, 2000);
      }
    },
    provide() {
      return {
        icons: {
          checked : "far fa-check-circle",
          unchecked: "far fa-circle"
        },
        // doneCount: computed(() => {
        //   return this.songs.filter((s) => s.done === true).length
        // })
        doneCount: this.songs.filter((s) => s.done === true).length
        
      }
    },
  }
</script>

<style scoped>
  @import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.14.0/css/all.min.css");
</style>