<template>
  <div class="fixed top-0 left-0 h-full w-full bg-black z-10 opacity-70"></div>
  <div class="bg-white w-96 h-full fixed right-0 top-0 z-20 p-8">

    <DrawerHeader/>

    <div v-if="!totalPrice"
         class="flex h-full items-center">
      <InfoBlock
          title="Корзина пустая"
          description="Добавьте хотя бы одн товар, чтобы сделать заказ"
          image-url="/package-icon.png"
      />
    </div>

    <div v-else>
      <DrawerCardList/>

      <div class="flex flex-col gap-4 mt-7">
        <div class="flex gap-2 ">
          <span>Score:</span>
          <div class="flex-1 border-b border-dashed"></div>
          <b>{{ totalPrice }} rub. </b>
        </div>

        <div class="flex gap-2 ">
          <span>Plati babki 5%: </span>
          <div class="flex-1 border-b border-dashed"></div>
          <b>{{ vatPrice }} rub.</b>
        </div>

        <button
            @click="() => emit('createOrder')"
            :disabled="buttonDisabled"
            class="mt-4 bg-lime-500 w-full rounded-xl py-3 text-white disabled:bg-slate-300 hover:bg-lime-600 transition active:bg-lime-700 cursor-pointer"
        >
          Pay
        </button>
      </div>
    </div>
  </div>
</template>


<script setup>
import DrawerHeader from "./DrawerHeader.vue";
import DrawerCardList from "./DrawerCardList.vue";
import {computed} from "vue";
import InfoBlock from "./InfoBlock.vue";

defineProps({
  totalPrice: Number,
  vatPrice: Number,
  buttonDisabled: Boolean,
})

const emit = defineEmits(['createOrder'])

</script>