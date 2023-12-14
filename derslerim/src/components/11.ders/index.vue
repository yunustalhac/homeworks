<script setup lang="ts">
import {onMounted, onUnmounted, ref} from "vue";

const modal = ref()
const show = true

onMounted(()=>{
  console.log(modal.value)

})

const color = ref("rgb(0, 0, 0)");
onMounted(() => {
  alert("lifecycle hookslar işlendi")
})


const random = () => {
  const red = Math.floor(Math.random() * 256); // 0 ile 255 arasında rastgele bir sayı
  const green = Math.floor(Math.random() * 256);
  const blue = Math.floor(Math.random() * 256);

  color.value = `rgb(${red},${green},${blue})`
}

</script>

<template>
  <h1>11.ders</h1>

  <h4>class binding ve style binding işlendi</h4>
  {{ color }}

  <p :class="{'bgc':show}" :style="{backgroundColor:color}">burada 11.videonun çalışması bulunur</p>
  <button @click="random">değiştir</button>

  <input placeholder="template ref" type="text" ref="modal">

</template>

<style scoped>

.bgc {
  color: beige;
}

</style>