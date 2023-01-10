<template>
  <div class="black-bg" v-if="modalStatus == true">
    <div class="white-bg">
      <h4>{{ oneRooms[param].title }}</h4>
      <p>{{ oneRooms[param].content }}</p>
      <input @input="month = $event.target.value">
      <p>{{month}} 개월 선택함 : {{ oneRooms[param].price * month}}</p>
      <button @click="close">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Modal',
    data(){
      return {
          month : 1
      }
    },
    props: {
        oneRooms : Array,
        param: Number,
        modalStatus:Boolean
    },
    methods: {
      close() {
        this.$emit('closeModal')
      }
    }
}
</script>

<style>

</style>