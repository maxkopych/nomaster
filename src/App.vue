<template>
  <div id="app">
    <Form @submited="formSubmited"></Form>
  </div>
</template>

<script>
  import Form from "./components/Form"
export default {
  name: 'notemaster',
  components:{
    Form,
  },
  data () {
    return {
      notes: []
    }
  },
  methods:{
    formSubmited(value){
      this.notes.push(value);
      console.log(this.notes);
    }
  }
}
</script>

<style>
</style>
