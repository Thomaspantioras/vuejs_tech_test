<template>
  <div class="banner">
    <picture>
      <source media="(min-width: 900px)" :srcset="images.large">
      <source media="(min-width: 600px)" :srcset="images.medium">
      <img id="banner-image" :src="images.small" alt="mountains and clear sky">
    </picture>
    <div class="centered">
      <p>{{ imageText }}</p>
    </div>
  </div>
</template>
 
<script>
export default {
  data() {
    return {
      images: {
        small: require('../assets/images/image-small-105422.jpg'),
        medium: require('../assets/images/image-medium-105422.jpg'),
        large: require('../assets/images/image-large-105422.jpg')
      },
      imageText: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit...'
    };
  }
};
</script>
 
<style>
.banner {
  position: relative;
  font-weight: bold;
  color: #314246;
  font-size: 1.2em;
}
#banner-image {
  width: 100%;
}
.centered {
  position: absolute;
  top: 35%;
  left: 72%;
  transform: translate(-50%, -50%);
}
</style>