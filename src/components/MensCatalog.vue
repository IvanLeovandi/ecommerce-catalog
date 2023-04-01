<template>
    <div class="container">
        <div class="card">
            <div class="card-img">
                <img :src="products.image" alt="">
            </div>
            <div class="card-desc">
                <h1>{{ products.title }}</h1>
                <div class="subheading">
                    <p>{{ products.category }}</p>
                    <span>{{ products.rating }}/5</span>
                </div>
                <hr>
                <p class="description">{{ products.description }}</p>
                <hr>
                <h2>${{ products.price }}</h2>
                <div class="button">
                    <a href="#" class="buy">Buy Now</a>
                    <a href="#" class="next">Next product</a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "MensCatalog",
    data: function() {
        return {
            products: [],
            idx: 0
        }
    },
    mounted: async function() {
        await fetch('https://fakestoreapi.com/products/1')
            .then(response => response.json())
            .then(data => {
                this.products = data;
            });
    }
}
</script>