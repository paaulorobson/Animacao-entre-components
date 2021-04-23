<template>
  <div id="app">
    <ul>
      <li @click="componenteAtivo = 'About'">Sobre</li>
      <li @click="componenteAtivo = 'Services'">Serviços</li>
    </ul>
    <transition mode="out-in">
      <component :is="componenteAtivo"></component>
    </transition>
  </div>
</template>

<script>
import About from './pages/About'
import Services from './pages/Services'


export default {
  name: 'App',
  components: {
    About,
    Services
  },
  data() {
    return {
      componenteAtivo: 'About'
    }
  }
  
}
</script>

<style>

.v-enter-active, .v-leave-active {
  transition: all .3s;

}

.v-enter, .v-leave-to {
  opacity: 0;
  transform: translate3d(0, -20px, 0);
}


</style>
