<script>
import MensCatalog from "./components/MensCatalog.vue";
import WomensCatalog from "./components/WomensCatalog.vue";
import UnavailProduct from "./components/UnavailProduct.vue";
import SkeletonLoader from "./components/SkeletonLoader.vue";

export default {
  name: "App",
  data: function() {
    return {
      isLoading: true,
      products: [],
      idx: 1,
      rateValue: 0
    }
  },
  components: {
    SkeletonLoader,
    MensCatalog,
    WomensCatalog,
    UnavailProduct
  },
  methods: {
    async fetchData() {
        await fetch(`https://fakestoreapi.com/products/${this.validIdx}`)
        .then(response => response.json())
        .then(data => {
            this.isLoading = false;
            this.products = data;
        });
    },
    changeWidth(position){
      console.log(position);
      this.find(".percent").css("width", position + "%");
    }
  },
  mounted() {
    this.fetchData()
  },
  computed: {
    validIdx() {
      return this.idx > 20
        ? this.idx = 1
        : this.idx = this.idx
    },
    dotWidth() {
      console.log(position);
      return this.rateValue = this.products.rating.rate * 100 / 5
    }
  },
  watch: {
    idx() {
      this.isLoading = true;
      this.fetchData()
    },
    rateValue() {
      this.changeWidth(rateValue);
    }
  }
    
};
</script>

<template>
  <div>
    <skeleton-loader v-if="isLoading"></skeleton-loader>
    <div v-else>
      <mens-catalog :product="products" v-if="this.products.category == 'men\'s clothing'" @nextProduct="() => this.idx++"></mens-catalog>
      <womens-catalog :product="products" v-else-if="this.products.category == 'women\'s clothing'" @nextProduct="() => this.idx++"></womens-catalog>
      <unavail-product v-else @nextProduct="() => this.idx++"></unavail-product>
    </div>
  </div>
</template>
