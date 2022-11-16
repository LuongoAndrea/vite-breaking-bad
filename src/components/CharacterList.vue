<template>
    <div class="container ">
        <div class="col-lg-12 d-flex cardC"> 
            <div class="character" v-for="(item,index) in characters" key="item.id">
                <img :src="item.img" :alt="item.name">
                <h1>{{item.name}}</h1>
                <h2>{{item.status}}</h2>
            </div>
        
        </div>
    </div>
</template>

<script>
    export default {
        name:'CharacterList',
        props: ['characters']
    }
</script>

<style lang="scss" scoped>
    .character{
        width: calc(100% / 4);
        img{
            width: 100%;
        }
    }
    .cardC{
        flex-wrap: wrap;
    }
</style>