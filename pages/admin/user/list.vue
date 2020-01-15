<template>
<section>
  <div class="head">
    <h1>Liste des utilisateurs</h1>
  </div>
  <div>
    <nuxt-link class="Add-stylus" to="NewUser">New User</nuxt-link>
  </div>
  <table class="table">
    <thead>
      <tr>
        <th scope="col">Nom Prénom</th>
        <th scope="col">Équipe</th>
        <th scope="col">Niveau</th>
        <th scope="col">Nombre de formations</th>
        <th scope="col">Actions</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><img src="" alt="">Olzack Henry</td>
        <td>2</td>
        <td>1</td>
        <td>29</td>
        <td><button class="mainbutton">Voir</button> | <button class="deletebutton">Delete</button></td>
      </tr>
      <tr>
        <td><img src="" alt=""> Mozavick Patrick</td>
        <td>4</td>
        <td>1</td>
        <td>19</td>
        <td><button class="mainbutton">Voir</button> | <button class="deletebutton">Delete</button></td>
      </tr>
    </tbody>
  </table>

  <p>
  <button >Previous</button> 
  <button >Next</button>
  </p>
</section>
</template>


<script lang="ts">

</script>

<style lang="scss">
  .Add-stylus{
    background-color: rgb(130, 211, 222);
    padding: 10px;
    border-radius: 9px;
    color: white;
    font-weight: bold;
  }

  button{
    &.deletebutton{
      background-color: rgb(255, 86, 86);
      border-color:rgb(255, 86, 86);
      padding: 8px;
      color: white;
      margin: 3px;
      border-radius: 9px;
    }
    &.mainbutton{
      background-color: rgb(130, 211, 222);
      border-color:rgb(130, 211, 222);
      padding: 8px;
      color: white;
      margin: 3px;
      border-radius: 9px;
    }
  }
  
  table{
    width: 100%;
  }
  tbody{
    & tr{
      height: 68px;
      & td:first-child { border-top-left-radius: 10px; border-bottom-left-radius: 10px; }
      & td:last-child { border-top-right-radius: 10px; border-bottom-right-radius: 10px; }
      &:hover{
        background-color: rgb(130, 211, 222);
      }
      & td{
        text-align: center;
      }
    }
  }
  
   div.head{
    min-height: 60px;
  }
</style>