<script>

import { store } from "../data/store"

export default {
    name: "card",
    data() {
        return {
            store
        }
    },

}
</script>
<template>
    <div class="container d-flex justify-content-center align-items-center flex-wrap">
        <div v-for="i in store.AllPokemons "
            class="cards col-sm-4 col-lg-2 d-flex  flex-column justify-content-ceter align-items-center">
            <img :src="i.imageUrl" :alt="i.name">
            <h4 my-4>{{ i.name }}</h4>
            <div class="type d-flex justify-content-between align-items-center w-80">
                <h4>{{ i.type1 }}</h4>
                <h4 v-if="i.type2">{{ i.type2 }}</h4>

            </div>

        </div>

    </div>

</template>

<style scoped lang="scss">
h4 {
    margin: 3px 0;
    text-align: center;
    color: white;
}

.type {
    width: 80%;
    margin: 0 auto;


}

.cards {
    height: 270px;
    border: 3px solid grey;
    padding: 50px;
    border-radius: 5px;
    background-image: linear-gradient(red, black, white);

    img {
        border-radius: 50%;
        width: 100px;
        height: 100px;
        box-shadow: 3px 5px grey;

    }
}
</style>