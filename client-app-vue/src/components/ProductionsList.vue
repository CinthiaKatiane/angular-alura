<template>
  
  <div class="list-productions">
    <h3>Lista de Produções</h3>
    <b-list-group>
      <b-list-group-item v-for="production of productions">
        <a class="text-justify" :href="production.uri">
          {{production.nome}}
        </a>
      </b-list-group-item>
    </b-list-group>
  </div>

</template>

<script>

export default {
  name: 'ProductionsList',
  data(){
    return {
      productions: []
    }
  },
  created(){
    let promise = this.$http.get('https://dadosabertos.camara.leg.br/api/v2/deputados');
    promise
        .then(res => res.json())
        .then(prod => this.productions = prod.dados);    

  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
  text-align: left;
}
</style>
