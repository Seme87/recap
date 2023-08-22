<script>
    
    import { store } from '../store';

    
    import CardCharacter from './CardCharacter.vue';
    

    export default {

        components:{CardCharacter},

        setup () {

            // const posts = ref(null);

            // onMounted(() => {
            //     axios.get("https://rickandmortyapi.com/api/character")
            //     .then((res)=> {
            //         console.log(res.data.results);
            //         posts.value = res.data.results;
            //         console.log(posts.value);
            //     })
            // } )

            return { store}
        }
    }
</script>


<template>
    <section class="container">
        <div class="row gy-4" v-if="store.posts.length > 0">
             <CardCharacter v-for="post in store.posts" :key="store.posts.id" class="col-sm-6 col-lg-3" :posts="post" />
        </div>
         <div class="text-center " v-else>
            <h2 class=" text-danger">La ricerca non ha prodotto risultati!</h2>
        </div>
    </section>
</template>

<style lang="scss" scoped>

</style>