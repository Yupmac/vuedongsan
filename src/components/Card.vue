<template>
  <div v-for="(data,i) in products" :key="i">
  <img :src="data.image" class="room-img">
  <!-- <h4 @click="modal = true; choice = i">{{ data.title }}</h4> -->
  <p>{{ data.price }}만원</p>
</div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    products : Array,
    choice : Number,
  }
}
</script>

<style>

</style>