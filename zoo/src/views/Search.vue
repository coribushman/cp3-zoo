<template>
<div>
  <div class="wrapper">
    <div class="search">
      <form class="pure-form">
        <i class="fas fa-search"></i><input v-model="searchText" />
      </form>
    </div>
  </div>
  <AnimalList :animals="animals" />
  <div class="footer">
    <a href='https://github.com/coribushman/cp3-zoo'>Github</a>
  </div>
</div>
</template>

<script>
import AnimalList from "../components/AnimalList.vue"
export default {
  name: 'Search',
  components: {
    AnimalList
  },
  data() {
    return {
      searchText: '',
    }
  },
  computed: {
    animals() {
      return this.$root.$data.animals.filter(animal =>
        animal.type.toLowerCase().search(this.searchText.toLowerCase()) >= 0);
    },

  },
}
</script>

<style scoped>
  .wrapper {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .search {
    border: 1px solid #ccc;
    border-radius: 4px;
    width: 50%;
  }

  form {
    display: table;
    width: 100%;
  }

  i {
    display: table-cell;
    padding-left: 10px;
    width: 1px;
  }

  input {
    display: table-cell;
    font-size: 20px;
    border: none !important;
    box-shadow: none !important;
    width: 100%;
    height: 40px;
  }

  .footer {
    display: flex;
    justify-content: center;
    margin-top: 20px;
    padding: 20px;
    background-color: #bcccc0;
    align-items: center;
  }


</style>
