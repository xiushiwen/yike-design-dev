<template>
  <yk-scrollbar height="400px" native>
    <div>
      <p v-for="item in 20" :key="item" class="item">{{ item }}</p>
    </div>
  </yk-scrollbar>
</template>
