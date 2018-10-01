<template>
  
  <div>
    <div class='search'>
      <b-tabs>
        <b-tab title="Produção" active>
          <br>
          <b-form-input type="text" v-model="busca" placeholder="Buscar produção"></b-form-input>
          <br>
          <p>
          lorem ipsum dolor sit amet, deism sa? </p>
          <br>
          <p>Busca Conjunta</p>
          <b-form-select v-model="selected" :options="options" class="mb-3" />
          
          <!-- Using components -->
          <b-input-group>
            <b-form-input></b-form-input>
            <b-input-group-append>
              <b-btn variant="info">Ir</b-btn>
            </b-input-group-append>
          </b-input-group>
        
        </b-tab>
        
        <b-tab title="Pesquisador" disabled>
          <br>I'm the second tab content
        </b-tab>
        <b-tab title="Grupo" disabled>
          <br>Disabled tab!
        </b-tab>
      </b-tabs>
    </div>
    
    <div class="filter">
    <b-card no-body class="mb-1">
      <b-card-header header-tag="header" class="p-1" role="tab">
        <b-btn block href="#" v-b-toggle.accordion1 variant="info">PRODUÇÃO</b-btn>
      </b-card-header>
      <b-collapse id="accordion1" visible accordion="my-accordion" role="tabpanel">
        <b-card-body>
          <p class="card-text">
            I start opened because <code>visible</code> is <code>true</code>
          </p>
          <p class="card-text">
            {{ text }}
          </p>
        </b-card-body>
      </b-collapse>
    </b-card>
    <b-card no-body class="mb-1">
      <b-card-header header-tag="header" class="p-1" role="tab">
        <b-btn block href="#" v-b-toggle.accordion2 variant="info">INSTITUIÇÃO</b-btn>
      </b-card-header>
      <b-collapse id="accordion2" accordion="my-accordion" role="tabpanel">
        <b-card-body>
          <p class="card-text">
            {{ text }}
          </p>
        </b-card-body>
      </b-collapse>
    </b-card>
    <b-card no-body class="mb-1">
      <b-card-header header-tag="header" class="p-1" role="tab">
        <b-btn block href="#" v-b-toggle.accordion3 variant="info">OUTROS</b-btn>
      </b-card-header>
      <b-collapse id="accordion3" accordion="my-accordion" role="tabpanel">
        <b-card-body>
          <p class="card-text">
            {{ text }}
          </p>
        </b-card-body>
      </b-collapse>
    </b-card>
          
    </div>
  </div>

</template>

<script>

export default {
  name: 'Filters',
  data () {
    return {
      busca: '',
      selected: null,
      options: [
        { value: null, text: '...' },
        { value: 'a', text: 'Pesquisador(a)' },
        { value: 'b', text: '...' },
        { value: 'c', text: '...', disabled: true }
      ]
    }
  },
  computed: {
    search(){
      if (this.data){
        let exp = new RegExp(this.data.trim(), 'i');
          return this.fotos.filter(foto => exp.test(foto.titulo));
      } else {
        return this.data
      }
    }
  }
}

</script>

<style scoped>
.search{
  position: block;
  margin: 40px 0 0;
  border: 1px solid grey;
  border-radius: 5px;
  padding: 10px;
}

.filter{
  margin: 40px 0 0;
  position: block;
  
}

h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 0px;
}
a {
  color: white;
  font-size: 12px;
}
</style>
