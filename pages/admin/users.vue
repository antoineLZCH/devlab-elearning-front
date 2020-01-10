<template>

 <div>
   <div class="font-sans antialiased h-screen">
      <Navbar/>
      <div id="main" class="pt-16">
        <Aside/>
        <div id="Content">    
              <Users>
                <div>
                  <h1>Liste des utilisateurs</h1>
                  <a class="Add-stylus" href="">New User</a>
                </div>
              <table class="table">
                <thead>
                  <tr>
                    <th scope="col">Nom Prénom</th>
                    <th scope="col">Équipe</th>
                    <th scope="col">Niveau</th>
                    <th scope="col">Nombre de formations</th>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <td><img src="" alt="">Name</td>
                    <td>2</td>
                    <td>1</td>
                    <td>29</td>
                  </tr>
                  <tr>
                    <td><img src="" alt=""> Mozavick Patrick</td>
                    <td>4</td>
                    <td>1</td>
                    <td>19</td>
                  </tr>
                </tbody>
              </table>
              <p>
              <button @click="prevPage">Previous</button> 
              <button @click="nextPage">Next</button>
              </p>
              </Users>
        </div>
      </div>
    </div>
 
 </div>
</template>


<script lang="ts">
import Vue, {PropOptions} from 'vue';
// import Navbar from '~/components/Navbar'
// import Aside from '~/components/Aside'

</script>

<style lang="scss">
  .Add-stylus{
    background-color: #82d3de;
    padding: 10px;
    border-radius: 9px;
    color: white;
    font-weight: bold;
  }
  
  table{
    width: 100%;
  }
  tbody{
    & tr{
      height: 68px;
      &:hover{
        background-color: rgb(130, 211, 222);
      }
      & td{
        text-align: center;
      }
    }
  }
</style>