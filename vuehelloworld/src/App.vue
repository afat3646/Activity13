
<script>
import axios from 'axios';
export default{
  data(){
    return{
      ID:"",
      notes: []
      }
      
  },
  mounted(){
    console.log("on mounted");
    axios.get('http://127.0.0.1:8000/api/notes').then(response=>{
      console.log(response.data)
      this.notes = response.data
    })
  },
  methods:{
    searchnotes(){
      this.foundnotes = this.notes.find(cat => cat.id === parseInt(this.ID))
    }
  }

}
</script>

<template>
  <div class="container">
    <div class="row mb-4">
      <div class="col">
        <h1>Notes system</h1>

      </div>
    </div>
    <div class="row justify-content-center">
      <div class="col-12 col-md-6">
        <label for="" class="form-label">Request</label>
        <input type="text" class="form-control-mb-3" v-model="ID" placeholder="Insert ID to search">
        <br>
        <button class="btn btn-primary mb-3" @click="searchnotes">Search</button>
        <div v-if="foundnotes">
          <p><strong>Title:</strong>{{ foundnotes.Title }}</p>
          <p><strong>Content:</strong>{{ foundnotes.Content }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>
