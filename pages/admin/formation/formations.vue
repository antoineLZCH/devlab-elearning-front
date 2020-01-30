<template>
<section>
  <div class="head">
    <h1>Liste des Formations</h1>
  </div>
  <div class="filters">
    <nuxt-link class="Add-stylus" to="NewFormation">New Formation</nuxt-link>
    <section class="bg-indigo-dark h-50 p-2">
              <div class="container mx-auto">
                <input v-model="search" class="w-full h-16 px-3 rounded focus:outline-none focus:shadow-outline text-xl px-8 shadow-lg" type="search" placeholder="Search ...">
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
      <tr v-for="formations in formationSearch" :key="formations.id" >
        <td>{{ formations.formation_name }}</td>
        <td>{{ formations.level }}</td>
        <td>{{ formations.chapter_nbr }}</td>
        <td><nuxt-link :to="'edit/'+formations.id" class="mainbutton">Edit</nuxt-link> | <button class="deletebutton">Delete</button></td>
      </tr>
    </tbody>
  </table>
  </div>

    <div class="search_result" v-if="formationSearch.length === 0">Pas de résultat</div>
    <div class="rows_number">Affichage de {{ formationSearch.length }} sur {{ formationSearch.length }} résultats</div>
    <div :class="{ 'disabled' : formationSearch.length === 0}" class="pagination_container"><jw-pagination :pageSize="5" :maxPages="5" :items="formations" @changePage="onChangePage" :labels="customLabels"></jw-pagination></div>
   
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

export default {
    data() {
        return {
          sortkey: 'name',
          reverse: false,
          columns: ['Nom', 'Niveau', 'Nombre de Chapitre', 'Actions'],
          search: '',
          customLabels,
          pageOfItems: [],
          formations: [
          { id: 1, formation_name: 'Formation 1', level: '3', chapter_nbr: '2' },
          { id: 2, formation_name: 'Formation 2', level: '3', chapter_nbr: '1' },
          { id: 3, formation_name: 'Formation 3', level: '3', chapter_nbr: '1'  },
          { id: 4, formation_name: 'Formation 4', level: '2', chapter_nbr: '2' },
          { id: 5, formation_name: 'Formation 5', level: '3', chapter_nbr: '4' }
        ]
        };
    },
    methods: {
        onChangePage(pageOfItems) {
            this.pageOfItems = pageOfItems;
        }
    },
    computed: {
    formationSearch() {
      return this.pageOfItems.filter(formations => {
        return formations.formation_name.toLowerCase().includes(this.search.toLowerCase())
      })
    }
  }
};
</script>

<style lang="scss">
  .Add-stylus{
    background-color: rgb(130, 211, 222);
    padding: 10px;
    border-radius: 10px;
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
      border-radius: 10px;
    }
    &.mainbutton{
      background-color: rgb(130, 211, 222);
      border-color:rgb(130, 211, 222);
      padding: 8px;
      color: white;
      margin: 3px;
      border-radius: 10px;
    }
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
  .rows_number{
    margin: 10px;
    text-align: center;
    opacity: 0.6;
  }
</style>