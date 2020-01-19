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
      <tr v-for="users in pageOfItems" :key="users.id">
        <td><img src="" alt="">{{ users.first_name }}</td>
        <td>{{ users.team }}</td>
        <td>{{ users.level }}</td>
        <td>{{ users.formation_nbr }}</td>
        <td><button class="mainbutton">Voir</button> | <button class="deletebutton">Delete</button></td>
      </tr>
    </tbody>
  </table>

    <div class="card-footer pb-0 pt-3"><jw-pagination :items="users" @changePage="onChangePage"></jw-pagination></div>
   
  </section>
</template>

<script lang="ts">
import Vue from 'vue'
import JwPagination from 'jw-vue-pagination';

Vue.component('jw-pagination', JwPagination);

export default {
    data() {
        return {
            pageOfItems: [],
            users: [
          { id: 1, first_name: 'Fred Flintstone', team: '3', level: '2', formation_nbr: '5' },
          { id: 2, first_name: 'Wilma Flintstone', team: '3', level: '2', formation_nbr: '5' },
          { id: 3, first_name: 'Barney Rubble', team: '3', level: '2', formation_nbr: '5'  },
          { id: 4, first_name: 'Betty Rubble', team: '3', level: '2', formation_nbr: '5'  },
          { id: 5, first_name: 'Pebbles Flintstone', team: '3', level: '2', formation_nbr: '5'  },
          { id: 6, first_name: 'Bamm Bamm Rubble', team: '3', level: '2', formation_nbr: '5'  },
          { id: 7, first_name: 'The Great Gazzoo', team: '3', level: '2', formation_nbr: '5'  },
          { id: 8, first_name: 'Rockhead Slate', team: '3', level: '2', formation_nbr: '5'  },
          { id: 9, first_name: 'Pearl Slaghoople', team: '3', level: '2', formation_nbr: '5'  },
          { id: 10, first_name: 'Pearl Slaghoople', team: '3', level: '2', formation_nbr: '5'  },
          { id: 11, first_name: 'Pearl Slaghoople', team: '3', level: '2', formation_nbr: '5'  },
          { id: 12, first_name: 'Pearl Slaghoople', team: '3', level: '2', formation_nbr: '5'  },
          { id: 13, first_name: 'Pearl Slaghoople', team: '3', level: '2', formation_nbr: '5'  },
          { id: 14, first_name: 'Pearl Slaghoople', team: '3', level: '2', formation_nbr: '5'  },
          { id: 15, first_name: 'Pearl Slaghoople', team: '3', level: '2', formation_nbr: '5'  },
        ]
        };
    },
    methods: {
        onChangePage(pageOfItems) {
            // update page of items
            this.pageOfItems = pageOfItems;
        }
    }
};
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