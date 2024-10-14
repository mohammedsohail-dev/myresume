<template>
    <div :class = "['details', darkmode]">
        <p :class = "['text', darkmode ]">
<img :src = "mobile" class = "deticon" /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(514) 569-1792 <br />
<br />
<img :src = "google" class = "deticon" />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;msohail17925@gmail.com <br />
<br />
<a href = "https://github.com/mohammedsohail-dev" >
<img :src = "github" class = "deticon" />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; mohammedsohail-dev (Github) <br />
</a>
<br />
<a href = "https://www.linkedin.com/in/mohammed-sohail-mahalti/" >
<img :src = "linkedin" class = "deticon" />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Mohammed Sohail Mahalti (LinkedIn) <br />
</a>
<br />
        </p>
    </div>
</template>

<script>


import { EventBus } from '../eventBus';
import google from '../assets/google_original.png';
import linkedin from '../assets/linkedin_original.png';
import github from '../assets/github_original.png';
import mobile from '../assets/mobile.png';

export default {
  name: "DetProp",
  components: {

  },
  data() {
    return {
      darkmode : 'dark',google,linkedin,github,mobile
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


.details.dark {
    position: fixed;
    left: 405px;
    top: 140px;
    width: 450px;
    height: 320px;
    background-color: rgba(22, 22, 22, 0.938);
    box-shadow: 1px 10px 10px black;

}

.text.dark {
    position: fixed;
    font-size: 20px;
    text-align: left;
    margin: 15px;
    color: white;
    text-shadow: 1px 1px 2px black;
    font-family: 'K2D', sans-serif;
    text-align: left;
    text-decoration: none;
}

.details.light {
    position: fixed;
    left: 405px;
    top: 140px;
    width: 450px;
    height: 320px;
    background-color: rgba(255, 255, 255, 0.801);
    box-shadow: 1px 10px 10px black;

}

.text.light {
    position: fixed;
    font-size: 20px;
    text-align: left;
    margin: 15px;
    color: rgb(0, 0, 0);
    text-shadow: 1px 1px 2px black;
    font-family: 'K2D', sans-serif;
}

.deticon {
  width: 24px;
  vertical-align: middle;
}

.text a {
    text-decoration: none; /* Remove underline from links */
    color: inherit; /* Inherit the text color from the parent */
}

@media (max-width: 768px) {

.details.dark {
    position: fixed;
    left: 0px;
    top: 40%;
    width: 60%;
    height: 10%;
    background-color: rgba(132, 0, 255, 0.637);
    box-shadow: none;

}

.text.dark {
    position: fixed;
    font-size: 6px;
    text-align: left;
    margin: 2%;
    color: white;
    text-shadow: 1px 1px 2px black;
    font-family: 'K2D', sans-serif;
    text-align: left;
    text-decoration: none;
}

.details.light {
  position: fixed;
    left: 0px;
    top: 40%;
    width: 60%;
    height: 10%;
    background-color: rgba(0, 255, 234, 0.801);
    box-shadow: none;

}

.text.light {
    position: fixed;
    font-size: 6px;
    text-align: left;
    margin: 2%;
    color: rgb(0, 0, 0);
    text-shadow: 1px 1px 2px rgb(0, 0, 0);
    font-family: 'K2D', sans-serif;
    text-align: left;
    text-decoration: none;
}

.deticon {
  width: 10px;
  vertical-align: middle;
}

.text a {
    text-decoration: none; /* Remove underline from links */
    color: inherit; /* Inherit the text color from the parent */
}

}

</style>