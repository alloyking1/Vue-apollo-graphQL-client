<template>
  <div class="main">
    <div class="row">
      <div class="container">
        <div class="col-md-12">
          <h1>To-Do APP With Vue.js Apollo and GraphQL</h1>
          <form>
            <div class="form-group">
              <input type="email" class="form-control" id="title" placeholder="Title">
            </div>
            <div class="form-group">
              <textarea class="form-control" id="todo" rows="3"></textarea>
            </div>
            <button type="button" class="btn btn-secondary btn-lg btn-block">Block level button</button>
          </form>
        </div>
      </div>
    </div>
    
    <div class="row">
      <div class="container mt-4">
        <div class="row">
          <div v-for="book in books" :key="book.id">
            <div class="col-md-4">
              <div class="card">
                <div class="card-body">
                  {{book}}
                </div>
              </div>
            </div>
          </div>
          </div>
        </div>
    </div>

  </div>
</template>

<script>
import gql from 'graphql-tag'

export default {
  data(){
    return{
      books:'',
    }
  },

  apollo:{
    books:{
      query: gql`
        query {
          books{
            title,
            author,
            description
          }
        }
      `,
    }
  }


  // this.books = this.$apollo.queries.books
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.main{
  padding-top: 5%;
}
</style>
