<template>
   <div>
    <img :src="oneRoom.image" class="room-img" alt='원룸'>
    <h2 @click="send">{{ oneRoom.title }}</h2>
  </div>
</template>

<script>
export default {
    name :'Card',
    props :{
        oneRoom : Object,
    },
    methods: {
        send() {
            this.$emit('openModal', this.oneRoom.id)
        }
    }
}
</script>

<style>

</style>