<template>
  <div class="about">
    <Titulo :contador="contador" :color="color" />
    <!--<h1
      :style="{'color': color}">
        Contador: {{contador}}
    </h1>-->
    <!--<button @click="aumentar">+</button>
    <button @click="disminuir">-</button>-->
    <hr>
    <input type="text" v-model="texto">
    <p>{{ texto }}</p>
    <Btn :textoBoton="'Aumentar'" @accion="aumentar" />
    <Btn :textoBoton="'Disminuir'" @accion="disminuir" />
  </div>
</template>

<script>
import Titulo from '../components/Titulo'
import Btn from '../components/Btn'
import { computed, ref } from 'vue'
export default {
  components: {
    Titulo,
    Btn
  },
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

    const color = computed(() => {
      if(contador.value < 0){
        return 'red';
      }else{
        return 'blue';
      }
    })
    return {contador, aumentar, disminuir, color, texto}
  },
}
</script>
