<template>
  <h1>contador: {{contador}}</h1>
  <Btn :textoBoton="'Aumentar'" @accion="aumentar" />
  <Btn :textoBoton="'Disminuir'" @accion="disminuir" />
</template>

<script>
import {useContador} from '../hooks/useContador'
import Btn from '../components/Btn'
export default {
  components: {
    Btn
  },
  setup(){
    return {...useContador()}
  }
}
</script>