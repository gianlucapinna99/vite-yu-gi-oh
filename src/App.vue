<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import axios from 'axios';
import { store } from './store';

export default {
  name: 'App',
  components: {
    AppHeader,
    AppMain
  },
  data() {
    return {
      store
    }
  },
  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php') //chiamata axios
      .then((response) => {
        this.store.cards = response.data.data;
        this.store.cardsNumber = response.data.data.length;
      })
  }
}
</script>

<template>
  <AppHeader></AppHeader>
  <AppMain></AppMain>
</template>

<style scoped></style>
