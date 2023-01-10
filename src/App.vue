<template>

  <DisCount></DisCount>
  <Modal @closeModal="modalStatus = false;" :oneRooms = "oneRooms" :param="param" :modalStatus="modalStatus"></Modal>


  <div class="menu">
    <a>Home</a>
    <a>Products</a>
    <a>About</a>
  </div>
  <Card @openModal="modalStatus = true; param = $event" :oneRoom = "oneRooms[index]" v-for="(oneRoom, index) in oneRooms" :key="index" ></Card>

</template>

<script>
import data from './post'
import DisCount from './Discount.vue'
import Modal from './Modal.vue'
import Card from './Card.vue'

export default {
  name: 'App',
  data() {
    return {
      param : 0,
      oneRooms : data,
      modalStatus: false,
      products : ['역삼동원룸' ,'천호동원룸', '마포구원룸'],
      신고수 : 0,
    }
  },
  methods :{
    increase() {
      this.신고수 += 1;
    }
  },
  components: {
    DisCount,
    Modal,
    Card
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
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a{
  color: white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

body {
  margin : 0
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position :fixed; padding: 20px;
}

.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}

.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}
</style>
