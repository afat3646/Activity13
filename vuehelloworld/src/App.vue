<script>
export default{
  data(){
    return{
      ID:"",
      Name:"",
      Class:"",
      DOB:"",
      Address:"",
      Phone:"",
      imageUrl:null

      
    }
  },
  methods: {
    onImageChange(event) {
      const file = event.target.files[0];
      if (file) {
        this.imageUrl = URL.createObjectURL(file); // Crea una URL temporal para mostrar la imagen
      }
    }
  }
  

}
</script>

<template>
  <div class="container">
    <div class="row mb-4">
      <div class="col">
        <h1 class="text-center">School ID</h1>
      </div>
    </div>
    <div class="row justify-content-center">
    <div class="col-12 col-md-6">
      <label for="" class="form-lable">ID</label><input type="text" class="form-control mb-3"v-model="ID">
      <br>
      <label for="" class="form-lable">Name</label><input type="text" class="form-control mb-3"v-model="Name">
      <br>
      <label for="" class="form-lable">Class</label><input type="text" class="form-control mb-3"v-model="Class">
      <br>
      <label for="" class="form-lable">D.O.B</label><input type="text" class="form-control mb-3"v-model="DOB">
      <br>
      <label for="" class="form-lable">Address</label><input type="text" class="form-control mb-3"v-model="Address">
      <br>
      <label for="" class="form-lable">Phone</label><input type="text" class="form-control mb-3"v-model="Phone">
      <br>

    </div>
    </div>
    <div class="container">
      <div class="row justify-content-center mt-5">
        <div class="col-12 col-md-6">
      
          <div class="input-group mb-3">
          <label class="input-group-text" for="inputGroupFile01">Attach image</label>
          <input type="file" class="form-control" id="inputGroupFile01">
          </div>
          <h2 class="text-center">Preview</h2>

          <div class="id-card">
            <br>
            <div v-if="imageUrl" class="image-container">
              <img :src="imageUrl" alt="ID Photo"class="id-photo">
            </div>

            <p><strong>ID:</strong> {{ ID }}</p>
            <p><strong>Name:</strong> {{ Name }}</p>
            <p><strong>Class:</strong> {{ Class }}</p>
            <p><strong>D.O.B:</strong> {{ DOB }}</p>
            <p><strong>Address:</strong> {{ Address }}</p>
            <p><strong>Phone:</strong> {{ Phone }}</p>
          </div>
          
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.id-card {
  background-color: #f9f9f9;
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 20px;
  max-width: 350px;
  margin: 0 auto;
  text-align: left;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.image-container {
  display: flex;
  justify-content: center;
  margin-bottom: 15px;
}

.id-photo {
  width: 100px; /* Ajusta el tamaño según tu preferencia */
  height: 100px; /* Ajusta el tamaño según tu preferencia */
  object-fit: cover;
  border-radius: 50%;
  border: 2px solid #ddd;
}

.id-card p {
  margin: 8px 0;
  font-size: 14px;
  color: #333;
}

.id-card p strong {
  color: #555;
}

.id-card-header {
  background-color: #007bff;
  color: white;
  padding: 10px;
  text-align: center;
  font-size: 18px;
  border-top-left-radius: 8px;
  border-top-right-radius: 8px;
}

.id-card-footer {
  text-align: center;
  font-size: 12px;
  color: #777;
  margin-top: 15px;
  padding-top: 10px;
  border-top: 1px solid #ddd;
}
</style>
