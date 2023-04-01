<template>
    <div class="u-container">
        <div class="card">
            <div class="skeleton-card-img">
            </div>
            <div class="m-card-desc">
                <h1 class="skeleton-heading"></h1>
                <div class="skeleton-subheading">
                    <p class="skeleton-category"></p>
                    <span class="skeleton-rate"></span>
                </div>
                <hr>
                <p class="skeleton-description"></p>
                <hr>
                <h2 class="skeleton-price"></h2>
                <div class="button">
                    <a href="#" class="skeleton-buy"></a>
                    <a href="#" class="skeleton-next"></a>
                </div>
            </div>
        </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      count: {
        type: Number,
        default: 4
      }
    }
  }
  </script>
  