<template>
  <img :src="image" alt="Desk of Drawers" class="main-image" />
</template>
  
  <script>
import image from "../../public/drawers.jpg";

export default {
  data() {
    return {
      image: image,
    };
  },
};
</script>
  
<style scoped lang="scss">
.main-image {
  width: 100%;
  height: 12.5rem;
  object-fit: cover;
  border-top-left-radius: 0.625rem;
  border-top-right-radius: 0.625rem;
}

@media screen and (min-width: 600px) {
  .main-image {
    height: 100%;
    border-bottom-left-radius: 0.625rem;
    border-top-right-radius: 0rem;
  }
}
</style>