<template>
    <main class="page-content">
        <section class="section products">
            <div class="container">
                <div class="row">
                    <div class="col-12 col-md-6 col-lg-4" v-for="product in products" :key="product.id">
                        <CardProduct :product="product"/>
                    </div>
                </div>
            </div>
        </section>
    </main>
</template>

<script>
import CardProduct from './CardProduct.vue';
import data from '../assets/db.json';


export default {
    components:{
        CardProduct,
        data,
    },
    data() {
        return {
            products: data.products
        }
    }
}

</script>

<style lang="scss">

</style>