<template>
    <div class = "photo">
    <img :src = "img" class = "image" />
    </div>
</template>

<script>

import img from '../assets/photo.jpeg';

export default {
  name: "PhotoProp",
  components: {

  },
  data() {
    return {
        img
    };
  }
};


</script>

<style>

.photo {
    position: fixed;
    left: 70px;
    top: 120px;
}

.image {
    position: fixed;
    width: 300px;
    height: 400px;
    box-shadow: 1px 10px 10px black;
}

</style>
