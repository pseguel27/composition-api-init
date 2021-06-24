<template>
  <div class="about">
   <h1>
      Contador: {{contador}}
    </h1>
    <button @click="aumentar">+</button>
    <button @click="disminuir">-</button>-->
  </div>
</template>

<script>
import { ref } from 'vue'
export default {
  //se ejecuta antes que se cree el componente, una vez que los props se resuelven, y es el punto de entrada para las API de composición
  //this desaparece, acceso directo a todos los datos
  setup() {
    //ref transforma nuestra constante en reactiva
    //ref(true) ref({}) ref([])
    const contador = ref(0);
    const texto = ref("");

    const aumentar = () => {
      contador.value ++
    }

    const disminuir = () => {
      contador.value --
    }
    return {contador, aumentar, disminuir}
  },
}
</script>
