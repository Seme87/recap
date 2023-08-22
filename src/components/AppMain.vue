<script>
    import { store } from '../store';
    import axios from 'axios';

    import SearchBar from './SearchBar.vue';
    import SectionCharacters from './SectionCharacters.vue';
    import { onMounted } from 'vue';


    export default {
        components:{SearchBar, SectionCharacters},
        setup () {
            onMounted(() => {
                // axios.get("https://rickandmortyapi.com/api/character")
                // .then((res)=> {
                //     console.log(res.data.results);
                //     store.posts = res.data.results;
                    
                // })
                searching();
            } )

            const searching = (data = '') => {
               if(data === 'reset'){
                store.searchText = ''
                store.statusValue = '';
               }
                axios.get("https://rickandmortyapi.com/api/character", {
                    params:{
                        name:store.searchText,
                        status:store.statusValue
                    }
                }).then((res)=> {
                    store.posts = res.data.results;
                }).catch((err)=>{
                    store.posts = [];
                })
            }

            return {store,searching}
        }
    }
</script>





<template>
    <main class="mt-5 mb-3">
        <SearchBar @search="searching" />
        <SectionCharacters />
       
    </main>
</template>



<style lang="scss" scoped>

</style>