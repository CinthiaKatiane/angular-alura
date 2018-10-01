<template>
  <div id="app">
    <Header msg="Rimor"/>

    <div class='container'>
      <div class="row">
        <Filters class='col-4'/>
        <ProductionsList class='col-8'/>
      </div>
    </div>
  </div>
</template>

<script>
import Header from './components/Header'
import Filters from './components/Filters'
import ProductionsList from './components/ProductionsList'

export default {
  name: 'app',
  components: {
    Header,
    ProductionsList,
    Filters
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}
</style>
