<script setup>
import CardItem from "./CardItem.vue";
import {inject} from "vue";

const {cart, removeFromCart} = inject('cart')

</script>

<template>
  <div class="flex flex-col gap-4 flex-1" v-auto-animate >
    <CardItem v-for="item in cart"
              :key="item.id"
              :title="item.title"
              :price="item.price"
              :image-url="item.imageUrl"
              @on-click-remove="() => removeFromCart(item)"
    />
  </div>
</template>

