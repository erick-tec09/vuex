<template>
 <div class="container">
     <div class="card__container">
         <div class="card m-4" v-for="(usuario, index) in usuarios" :key=" index" >
              <div class="card-image ">
                <figure class="image">
                  <img src="https://lh3.googleusercontent.com/proxy/tgl7GeNAiTYzVOzWYQ25r0xLAGnYWn9lCsG8N5X0iUui1_TlK8FMiAvbd5PEAJygt0i1qwwV1_afXvYtIw" alt="Placeholder image">
                </figure>
              </div>
              <div class="card-content">
                <div class="media">
                  <div class="media-content">
                    <p class="title is-4 ">Inicial: <span class="charAt">{{usuario.name.charAt(0)}}</span></p>
                    <p class="title is-4">Nombre:{{usuario.name}}</p>
                    <p class="subtitle is-6">Email:{{usuario.email}}</p>
                    <p class="subtitle is-6">Tel:{{usuario.phone}}</p>
                    <p class="subtitle is-6">Web: <a href="">{{usuario.website}}</a></p>
                  </div>
                </div>
                <footer class="card-footer">
                <a href="#" class="card-footer-item">Save</a>
                   <router-link  :to="{
                    
                    name:'Editar',
                    params:{ id: usuario.id}
                    }">

                   <a href="#" class="card-footer-item">Edit</a>
                </router-link>
              
                <a href="#" class="card-footer-item">Delete</a>
              </footer>
              </div>
          </div> 
     </div>
 
 </div>

</template>

<script>
export default {
  
 data() {
    return {
        usuarios: [],
        
    }
    
},
methods: {
  async getInfoUsers(){

    const info = await fetch('https://jsonplaceholder.typicode.com/users')
    const data = await info.json()

    console.log(data)
    this.usuarios = data
  }
        

    },
    created() {
      this.getInfoUsers();
    }
   
 
}
</script>

<style>
.card {
    width: 300px;
    border: 1px solid rgba(110, 109, 109, 0.466);
}
.image {
  
    width: 150px;
    margin: 0px auto;
}
.card__container {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
}
.charAt{

  color: #00D1B2;
}
</style>