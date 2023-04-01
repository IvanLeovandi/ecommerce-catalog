<template>
    <div class="u-container">
        <div class="u-card">
            <img src="../assets/sad-face.jpg" alt="sad face" class="sad-face">
            <div class="unavail-text">
                <p>This product is unavailable to show</p>
                <a href="#" class="u-next" @click.stop="$emit('nextProduct')">Next product</a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "UnavailProduct",
}
</script>