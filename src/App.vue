<template>
  <div class="app">
    <div class="wrapper">
      <Header />
      <Card />
    </div>
  </div>
</template>

<script>
import Header from './components/Header';
import Card from './components/Card';

export default {
  name: 'App',
  components: {
    Header,
    Card,
  },
  data() {
    return {};
  },
};
</script>
<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
#app {
  font-family: 'Roboto', sans-serif;
  background-color: #fff;
}
.wrapper {
  position: relative;
}
</style>
