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

@media (max-width: 768px) {
  .photo {
    position: fixed;
    left: 60%;
    top: 10%;
   }

.image {
    position: fixed;
    width: 40%;
    height: 40%;
    box-shadow: none;
}

}

</style>
