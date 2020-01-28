<template>
<section>
  <div class="head">
    <h1>Liste des utilisateurs</h1>
  </div>
  <div class="filters">
    <nuxt-link class="Add-stylus" to="NewUser">New User</nuxt-link>
    <!-- <select v-model="selectedValue" @change="onChange" class="appearance-none h-full rounded-l border block appearance-none w-full bg-white border-gray-400 text-gray-700 py-2 px-4 pr-8 leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
        <option value="5">5</option>
        <option value="10">10</option>
        <option value="15">15</option>
        <option value="20">20</option>
     </select> -->
    <section class="bg-indigo-dark h-50 p-2">
              <div class="container mx-auto">
                <input v-model="search" class="w-full h-16 px-3 rounded focus:outline-none focus:shadow-outline text-xl px-8 shadow-lg" type="search" placeholder="Search User...">
          </div>
      </section>
  </div>
  <div class="scrollable">
  <table class="table">
    <thead>
      <tr>
        <th v-for="column in columns" :key="column">
            <a href="#" @click="sortBy(column)">
              {{ column }}
            </a>
        </th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="users in userSearch" :key="users.id" >
        <td class="user_picture"><img src="../../../assets/img/avatar1.jpg" alt="user picture"></td>
        <td>{{ users.first_name }}</td>
        <td>{{ users.team }}</td>
        <td>{{ users.level }}</td>
        <td>{{ users.formation_nbr }}</td>
        <td><button class="mainbutton">Edit</button> | <button class="deletebutton">Delete</button></td>
      </tr>
    </tbody>
  </table>
  </div>
    <div class="search_result" v-if="userSearch.length === 0">Pas de résultat</div>

    <div class="rows_number">Affichage de {{ userSearch.length }} sur {{ users.length }} résultats</div>
    <div :class="{ 'disabled' : userSearch.length === 0}" class="pagination_container"><jw-pagination :pageSize="selectedValue" :items="users" @changePage="onChangePage" :labels="customLabels"></jw-pagination></div>
   
  </section>
</template>

<script lang="ts">
import Vue from 'vue'
import JwPagination from 'jw-vue-pagination';

Vue.component('jw-pagination', JwPagination);

const customLabels = {
    first: '<<',
    last: '>>',
    previous: '<',
    next: '>'
};

export default Vue.extend({
    data() {
        return {
          columns: ['','Nom Prénom', 'Équipe', 'Niveau', 'Nombre de formations', 'Actions'],
          search: '',
          selectedValue: 5,
          customLabels,
          pageOfItems: [],
          users: [
          { id: 1, first_name: 'Fred Flintstone', team: '3', level: '2', formation_nbr: '5' },
          { id: 2, first_name: 'Wilma Flintstone', team: '3', level: '1', formation_nbr: '5' },
          { id: 3, first_name: 'Barney Rubble', team: '3', level: '1', formation_nbr: '5'  },
          { id: 4, first_name: 'Betty Rubble', team: '2', level: '2', formation_nbr: '5'  },
          { id: 5, first_name: 'Pebbles Flintstone', team: '3', level: '4', formation_nbr: '5'  },
          { id: 6, first_name: 'Bamm Bamm Rubble', team: '3', level: '2', formation_nbr: '5'  },
          { id: 7, first_name: 'The Great Gazzoo', team: '3', level: '5', formation_nbr: '5'  },
          { id: 8, first_name: 'Rockhead Slate', team: '4', level: '2', formation_nbr: '5'  },
          { id: 9, first_name: 'Pearl Slaghoople', team: '3', level: '2', formation_nbr: '5'  },
          { id: 10, first_name: 'Pearl Slaghoople', team: '3', level: '2', formation_nbr: '5'  },
          { id: 11, first_name: 'Pearl Slaghoople', team: '3', level: '1', formation_nbr: '5'  },
          { id: 12, first_name: 'Pearl Slaghoople', team: '5', level: '2', formation_nbr: '5'  },
          { id: 13, first_name: 'Pearl Slaghoople', team: '3', level: '2', formation_nbr: '5'  },
          { id: 14, first_name: 'Pearl Slaghoople', team: '3', level: '8', formation_nbr: '5'  },
          { id: 15, first_name: 'Pearl Slaghoople', team: '3', level: '2', formation_nbr: '5'  },
        ]
        };
    },
    methods: {
        onChangePage(pageOfItems){
            this.pageOfItems = pageOfItems;
       },
       sortBy: function(sortKey) {
        this.reverse = (this.sortKey == sortKey) ? ! this.reverse : false;
        this.sortKey = sortKey;
       }
      //  ,
      //  onChange(selectedValue) {
      //   this.selectedValue = selectedValue;
      // }
    },
    computed: {
    userSearch(){
      return this.pageOfItems.filter(users => {
        return users.first_name.toLowerCase().includes(this.search.toLowerCase())
      })
    }
  }
});
</script>

<style lang="scss">
  .Add-stylus{
    background-color: rgb(130, 211, 222);
    padding: 10px;
    border-radius: 10px;
    color: white;
    font-weight: bold;
  }

 
  .deletebutton{
      background-color: rgb(255, 86, 86);
      border-color:rgb(255, 86, 86);
      padding: 8px;
      cursor: pointer;
      color: white;
      margin: 3px;
      border-radius: 10px;
    }
  .mainbutton{
      background-color: rgb(130, 211, 222);
      border-color:rgb(130, 211, 222);
      cursor: pointer;
      padding: 8px;
      color: white;
      margin: 3px;
      border-radius: 10px;
  }

  
  table{
    width: 100%;
    & thead tr{
      height: 70px;
    }
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
        &.user_picture{
          width: 5%;
          & img{
            border-radius: 10px;
          }
        }
      }
    }
  }

  .rows_number{
    margin: 10px;
    text-align: center;
    opacity: 0.6;
  }

  .search_result{
    text-align: center;
    font-size: 18px;
    color: rgb(255, 91, 91);
    margin-bottom: 20px;
  }
  
  .pagination_container{
    text-align: center;
    margin: 10px;
    & .page-item.disabled{
      color: gray;
    }
    &.disabled{
      display: none;
    }
    & .page-item.page-number.active{
      color: #ffffff;
      & a.page-link{
        background-color:rgb(130, 211, 222);
        border-radius: 10px
      }
    }
  }
  
   div.head{
    min-height: 38px;
  }

  .filters{
    display: flex;
    float: left;
    margin: 10px;
    & input{
      border-radius: 10px;
      height: 40px;
      font-size: 18px;
    }
  }

  @media only screen and (max-width: 600px){
    
    .scrollable{
      width: 100%;
      overflow: scroll;
      & table{
        width: 1000px;
      }
    }


  }
</style>