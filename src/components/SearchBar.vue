<script>
import { store } from '../store';
export default {
    setup () {
        

        return {store}
    }
}
</script>

<template>

    <div class="container mb-5">
        <form class="d-flex justify-content-center" @submit.prevent="$emit('search')">
            <input type="text" class="form-control w-auto mx-2" placeholder="Search Character" v-model="store.searchText" >
            <select class="form-select w-auto mx-2" v-model="store.statusValue">
                <option selected value="">select Status</option>
                <option value="alive">alive</option>
                <option value="dead">dead</option>
                <option value="unknown">unknown</option>
            </select>

            <button type="submit" class="btn btn-primary mx-2">Search</button>
            <button type="reset" class="btn btn-warning mx-2" @click="$emit('search', 'reset')">Reset</button>
        </form>
    </div>

</template>

<style lang="scss" scoped>

</style>