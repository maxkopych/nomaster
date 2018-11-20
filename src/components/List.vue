<template>
  <div class="row">
    <div class="item col-xs-12 col-sm-6 col-md-4" v-for="(item,key) in list">
      <div class="box card">
        <h1 class="card-header">{{item.title}}</h1>
        <article class="card-body">
          <div class="blockquote">{{item.text}}</div>
        </article>
        <button @click="deleteItem(key)" class="btn btn-danger mt-3">Delete</button>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "List",
    props: [
      "list"
    ],
    data(){
      return ({
      
      })
    },
    methods:{
      deleteItem(val){
        this.$emit("deleteItem",val);
      }
    }
  }
</script>

<style scoped>
.item{
  margin-bottom: 10px;
}
/*.box{
  border: 1px solid black;
  border-radius: 5px;
  padding: 10px;
}*/
</style>