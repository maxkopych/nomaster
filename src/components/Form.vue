<template>
  <div>
    <form>
      <div class="form-group">
        <label for="exampleInputEmail1">Title</label>
        <input type="email" v-model="title" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Enter email">
      </div>
      <div class="form-group">
        <label for="exampleInputPassword1">Note:</label>
        <textarea id="exampleInputPassword1" v-model="text" class="form-control"></textarea>
      </div>
      <button @click="sendToParent" type="submit" class="btn btn-primary">Create</button>
    </form>
  </div>
</template>

<script>
  export default {
    name: "Form",
    data(){
      return {
        title: "",
        text: ""
      }
    },
    methods:{
      sendToParent(){
        const note={
          title: this.title,
          text: this.text,
        };
        this.title="";
        this.text="";
        this.$emit("submited",note);
      }
    }
  }
</script>

<style scoped>

</style>