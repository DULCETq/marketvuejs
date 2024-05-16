<script setup>
defineProps({
  totalPrice: Number
})

 const emit = defineEmits(['openDrawer']);
</script>


<template>
  <header class="flex justify-between border-b border-slate-200 px-10 py-8">

    <div class="flex items-center gap-4">
      <img src="/logo.png" alt="logo" class="w-10">
      <div>
        <h2 class="text-xl font-bold uppercase">Market DCP</h2>
        <p class="text-slate-400">Duper computer puper</p>
      </div>
    </div>

    <ul class="flex items-center gap-10">
      <li @click="() => emit('openDrawer')"
          class="flex items-center gap-3 text-gray-500 hover:text-black cursor-pointer">
        <img src="/cart.svg" alt="cart">
        <b>{{ totalPrice }} rub.</b>
      </li>

      <li class="flex items-center gap-3 text-gray-500 hover:text-black cursor-pointer">
        <img src="/heart.svg" alt="heart">
        <span>Follows</span>
      </li>

      <li class="flex items-center gap-3 text-gray-500 hover:text-black cursor-pointer">
        <img src="/profile.svg" alt="profile">
        <span>Profile</span>
      </li>
    </ul>

  </header>
</template>