<template>
  <header>
    <HeaderComponent/>
  </header>
  <main>
    <SearchComponent/>
    <CharacterList/>
  </main>

</template>

<script>
  import axios from 'axios';
  import CharacterList from './components/CharacterList.vue';
  import HeaderComponent from './components/HeaderComponent.vue';
  import SearchComponent from './components/SearchComponent.vue';

  export default {
    components: { HeaderComponent, CharacterList, SearchComponent }
}
</script>

<style lang="scss" scoped>
  
</style>
