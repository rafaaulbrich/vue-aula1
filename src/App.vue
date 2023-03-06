<script setup>
import { ref, onMounted } from 'vue'

const contador = ref(0)

function incrementarContador() {
  contador.value++
}
function decrementarContador() {
    if (contador.value > 0) {
      contador.value--}
    else {
      alert(`Não é possível decrementar!`)
    }
}
function zerarContador() {
  contador.value = "0";
}

onMounted(() => {
  console.log(`O valor inicial do contador é ${contador.value}.`)
})
</script>

<template>
  <button @click="incrementarContador">Incrementar</button>
  <button @click="decrementarContador">Decrementar</button>
  <p>Valor do contador é: {{ contador }}</p><br><br>
  <button class="reinicia" @click="zerarContador">Reiniciar</button>
</template>

<style scoped>
.reinicia {
  margin-left: 50%;
}
button {
  font-weight: bold;
}
</style>
