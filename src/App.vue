<template>
<div  class = 'container'>
  <TopBar />
  <InfoProp />
  <PhotoProp />
  <DetailsProp />
  <EducationProp />
</div>

</template>

<script>
import DetailsProp from './components/details-prop.vue';
import EducationProp from './components/education-prop.vue';
import InfoProp from './components/info-prop.vue';
import PhotoProp from './components/photo-prop.vue';
import TopBar from './components/top-bar.vue';
import background from './assets/background.jpg';

export default {
  name: 'App',
  components: {
    TopBar, PhotoProp, EducationProp, InfoProp, DetailsProp
  },
  data() {
    return {
      background
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

html, body {
  background-color: rgb(26, 26, 26);
  margin: 0;
  padding: 0;
  height: 100%;
  width: 100%;
  background-image: url('./assets/background.jpg');
  position: 'fixed';
  background-size: cover;
}



</style>
