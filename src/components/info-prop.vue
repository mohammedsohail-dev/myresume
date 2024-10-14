<template>
    <div :class = "['info', darkmode ]">
        <p :class = "['text1', darkmode ]">
        {{info[0]}} <br />
        {{info[1]}}<br />
<br />
<br />
<br />
{{info[2]}} <br />
{{info[3]}}<br />
<br />
Java <br />
TypeScript <br />
MongoDB <br />
Vue.js <br />
Figma <br />
HTML <br />
CSS <br />
Python <br />
<br />
{{info[4]}}<br />
<br />
<br />
<br />
{{info[5]}} <br />
{{info[6]}}<br />





        </p>
    </div>
</template>

<script>

import { EventBus } from '../eventBus.js';


export default {
  name: "InfoProp",
  components: {

  },
  data() {
    return {
      darkmode : 'dark',
      language : 'FR',
      infoeng : [
        'WHO AM I ?', 'A Software engineer with a passion of creating I.T solutions and solving complex problems. I have a knack of troubleshooting and problem solving. Currently living in Montreal.','WHAT CAN I DO?',
        'I can create websites, content delivery networks, troubleshoot problems. The technologies generally I work with are:', 'and the list goes on... I am flexible with learning new technologies and creating I.T solutions which are right for you. Obviously with future scalability and minimal overhead costs. I am bilingual in French as well so I am the right candidate to make your website which might cater to a French as well as an English audience.','HOW TO REACH ME?'
        ,'I am currently searching for a job and I am available via email and LinkedIn personal message as well.In the meanwhile you can checkout my LinkedIn on my qualifications and projects.'
      ],
    infofr : [
      'QUI SUIS-JE?', "Un ingénieur logiciel passionné par la création de solutions informatiques et la résolution de problèmes complexes. J'ai un talent pour le dépannage et la résolution de problèmes. Vivant actuellement à Montréal.", "QUE PUIS-JE FAIRE ?", "Je peux créer des sites Web, des réseaux de diffusion de contenu, résoudre des problèmes. Les technologies avec lesquelles je travaille généralement sont :", "et la liste est longue... Je suis flexible pour apprendre de nouvelles technologies et créer des solutions informatiques qui vous conviennent. Évidemment avec une évolutivité future et des frais généraux minimes. Je suis également bilingue en français, je suis donc le bon candidat pour créer votre site Web qui pourrait s'adresser à un public français et anglais.",
      "COMMENT ME JOINDRE ?", "Je suis actuellement à la recherche d'un emploi et je suis également disponible par e-mail et par message personnel sur LinkedIn. En attendant, vous pouvez consulter mon LinkedIn sur mes qualifications et mes projets."
    ],
    info: []
    };
  },
  mounted() {
    this.info = this.infoeng;

    EventBus.on('toggledarkmode', (darkmode) => {
      if(darkmode === 'dark') {
         this.darkmode = 'light'
      } else {
        this.darkmode = 'dark'
      }
    });
    EventBus.on('togglelanguage', (language) => {
      if(language === 'FR') {
         this.language = 'EN',
         this.info = this.infofr
      } else {
        this.language = 'FR',
        this.info = this.infoeng
      }
    });

  }
};


</script>

<style>


@import url('https://fonts.googleapis.com/css2?family=K2D&display=swap');


.info.dark {
    position: fixed;
    right: 0px;
    top: 75px;
    width: 1060px;
    height: 100%;
    background-color: rgba(32, 32, 32, 0.61);

}

.text1.dark {
    position: fixed;
    font-size: 20px;
    text-align: left;
    margin: 15px;
    color: white;
    text-shadow: 1px 1px 2px black;
    font-family: 'K2D', sans-serif;
}

.info.light {
    position: fixed;
    right: 0px;
    top: 75px;
    width: 1060px;
    height: 100%;
    background-color: rgba(0, 81, 255, 0.171);

}

.text1.light {
    position: fixed;
    font-size: 20px;
    text-align: left;
    margin: 15px;
    color: white;
    text-shadow: 1px 1px 2px black;
    font-family: 'K2D', sans-serif;
}




</style>