<template>
  
    <HeaderComponent title="Breaking Bad" list=this.list[0].name />
  
  <main>
    <SearchComponent @filterchar="getCharacters" />
    <CharacterList :characters="list" />
  </main>

</template>

<script>
  import axios from 'axios';
  // import {store} from './store';
  import CharacterList from './components/CharacterList.vue';
  import HeaderComponent from './components/HeaderComponent.vue';
  import SearchComponent from './components/SearchComponent.vue';

  export default {
    components: { HeaderComponent, CharacterList, SearchComponent },
    data() {
      return {
        // store,
        // endPoint: 'characters',
        apiUrl: 'https://www.breakingbadapi.com/api/characters',
    list:[],
    loading: false,
    searchStatus: '',
    errorMessage: ''
      }
    },
    methods:{
      getCharacters(status) {
        if(status){
          this.apiUrl = this.apiUrl + '?status=' + status
        }
        axios.get(this.apiUrl).then(
          (res)=>{
            this.list=[...res.data];
            console.log(this.list);
            console.log(this.list[0].name)
          }
        );
      }
    },
    created(){
      this.getCharacters();
    }
}
</script>

<style lang="scss" scoped>
  
</style>
