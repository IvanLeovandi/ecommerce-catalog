<template>
    <div class="w-container">
        <div class="card">
            <div class="w-card-img">
                <img :src="product.image" alt="">
            </div>
            <div class="w-card-desc">
                <h1>{{ product.title }}</h1>
                <div class="subheading">
                    <p>{{ product.category }}</p>
                    <div class="rating">
                        <span class="rating-value">{{ product.rating.rate }}/5</span>
                        <!-- dotted rating -->
                        <span class="rating-dots dot-rating">
                            <span class="dots up-dot percent w-dot">
                                <i class="fa-solid fa-circle"></i>
                                <i class="fa-solid fa-circle"></i>
                                <i class="fa-solid fa-circle"></i>
                                <i class="fa-solid fa-circle"></i>
                                <i class="fa-solid fa-circle"></i>
                            </span>
                            <div class="dots down-dot w-dot">
                                <i class="fa-regular fa-circle"></i>
                                <i class="fa-regular fa-circle"></i>
                                <i class="fa-regular fa-circle"></i>
                                <i class="fa-regular fa-circle"></i>
                                <i class="fa-regular fa-circle"></i>
                            </div>
                        </span>
                    </div>
                </div>
                <hr>
                <p class="description">{{ product.description }}</p>
                <hr>
                <h2>${{ product.price }}</h2>
                <div class="button">
                    <a href="#" class="w-buy">Buy Now</a>
                    <a href="#" class="w-next" @click.stop="$emit('nextProduct')">Next product</a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "WomensCatalog",
    props: {
        product: {
        type: Object,
        required: true
        }
    },
}
</script>