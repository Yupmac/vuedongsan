<template>
    <div class="black-bg" v-if="modal === true">
    <div class="white-bg">
      <img :src="products[choice].image" style="width:50%">
      <h4>{{ products[choice].title }}</h4>
      <p>{{ products[choice].content }}</p>
      <p>{{ products[choice].price }}원</p>
      <!-- <button @click="modal = false">닫기</button> -->
    </div>
  </div>
</template>

<script>
export default {
  name : 'Modal',
  props : {
    products : Array,
    choice : Number,
    modal : Boolean,
  }
}
</script>

<style>

</style>