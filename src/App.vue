<template>
  <div class="container pt-2">
    <button class ="btn btn-primary" @click="loadResults" >Load results</button>

    <hr>

    <ul class="list-group">
      <li class="list-group-item" v-for="result of results">
        <strong> {{ result }} </strong> 
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        results: []
      }
    },
    methods: {
      loadResults () {
        this.$http.get('https://rickandmortyapi.com/api/character/info/count')
        .then(response => {
          return response.json()
        })
        .then(cars => {
          this.results = results
          console.log(results)
        }) 
      }
    }
  }
</script>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}
.body {
  display: flex;
  justify-content: center;
  align-items: center;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
