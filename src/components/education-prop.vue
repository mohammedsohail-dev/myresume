<template>
    <div :class = "[ 'education', darkmode ]">
        <p :class = "['text2', darkmode]">
        Concordia University, Montreal <br />
        Master of Engineering in Electrical <br />
        and Computer Engineering <br />
        2022 - 2023 <br />
        <br />
        <br />
        <br />
        Vellore Institute of Technology, Vellore <br />
        Bachelor of Engineering <br />
        in Electronics and Communication Engineering <br />
        2017 - 2021 <br />
        </p>
    </div>
</template>

<script>

import { EventBus } from '../eventBus';

export default {
  name: "EduProp",
  components: {

  },
  data() {
    return {
      darkmode : 'dark'
    };
  },
  mounted() {
    EventBus.on('toggledarkmode', (darkmode) => {
      if(darkmode === 'dark') {
         this.darkmode = 'light'
      } else {
        this.darkmode = 'dark'
      }
    })
  }

};


</script>

<style>


@import url('https://fonts.googleapis.com/css2?family=K2D&display=swap');


.education.dark {
    position: fixed;
    left: 70px;
    top: 540px;
    width: 450px;
    height: 320px;
    background-color: rgba(22, 22, 22, 0.938);
    box-shadow: 1px 10px 10px black;

}

.text2.dark {
    position: fixed;
    font-size: 20px;
    text-align: left;
    margin: 15px;
    color: white;
    text-shadow: 1px 1px 2px black;
    font-family: 'K2D', sans-serif;
}

.education.light {
    position: fixed;
    left: 70px;
    top: 540px;
    width: 450px;
    height: 320px;
    background-color: rgba(255, 255, 255, 0.801);
    box-shadow: 1px 10px 10px black;

}

.text2.light {
    position: fixed;
    font-size: 20px;
    text-align: left;
    margin: 15px;
    color: rgb(0, 0, 0);
    text-shadow: 1px 1px 2px black;
    font-family: 'K2D', sans-serif;
}




</style>