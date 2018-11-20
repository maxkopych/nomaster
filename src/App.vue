<template>
  <div id="app"  class="container my-5">
    <Form @submited="formSubmited"></Form>
    <hr>
    <List :list="notes" @deleteItem="deleteItem"></List>
  </div>
</template>

<script>
  import Form from "./components/Form"
  import List from "./components/List"
export default {
  name: 'notemaster',
  components:{
    Form,
    List
  },
  data () {
    return {
      notes: [{
        title: "Lorem ipsum",
        text: `Lorem ipsum dolor sit amet, consectetur adipisicing elit. Beatae debitis eaque maxime molestiae, quod soluta!`
      }]
    }
  },
  methods:{
    formSubmited(value){
      this.notes.push(value);
    },
    deleteItem(val){
      this.$delete(this.notes,val);
    }
  }
}
</script>

<style>
</style>
