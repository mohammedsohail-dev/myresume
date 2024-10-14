<template>
    <div :class = "['top', darkmode]">
        <div :class = "['title',darkmode]">
            Mohammed Sohail Mahalti
        </div>
        <div :class = "['language',darkmode]" @click = "togglelanguage">
            {{ language }}
        </div>
        <div :class = "['darklight',darkmode]">
            <img :src="icon" @click="togglemode" />
        </div>
    </div>
    </template>

    <script>

    import sun from '../assets/Sun.png';
    import moon from '../assets/Moon.jpg';
    import { EventBus } from '../eventBus.js';

    export default {
        name: 'top-bar',
          data() {
        return {
        darkmode : 'dark',
        icon : sun,
        sun,moon,
        language: 'FR'
      }
      },
      methods: {
        togglemode() {
            if(this.darkmode === 'dark') {
                EventBus.emit('toggledarkmode', this.darkmode),
                this.darkmode = 'light',
                this.icon = moon
            } else {
                EventBus.emit('toggledarkmode', this.darkmode),
                this.darkmode = 'dark',
                this.icon = sun
            }
            localStorage.setItem('darkmode', this.darkmode);
            localStorage.setItem('icon', this.icon);
        },

        togglelanguage() {
            if(this.language === 'FR') {
                EventBus.emit('togglelanguage', this.language),
                this.language = 'EN'
            } else {
                EventBus.emit('togglelanguage', this.language),
                this.language = 'FR'
            }
            localStorage.setItem('language', this.language);
        }
      }
    }

    </script>

    <style>

    .top.dark {
        position: fixed;
        background-color: black;
        left: 0px;
        top:  0px;
        height: 75px;
        width: 100%;
    }

    .title.dark {
        position : fixed;
        left: 20px;
        top: 24px;
        font-size: 24px;
        color: white;
    }

    .language.dark {
        cursor: pointer;
        position : fixed;
        right: 110px;
        top: 24px;
        font-size: 24px;
        color: white;
    }

    .darklight.dark {
        cursor: pointer;
        position : fixed;
        right: 60px;
        top: 24px;
        font-size: 24px;
        color: white;
    }


    .top.light {
        position: fixed;
        background-color: white;
        left: 0px;
        top:  0px;
        height: 75px;
        width: 100%;
    }

    .title.light {
        cursor: pointer;
        position : fixed;
        left: 20px;
        top: 24px;
        font-size: 24px;
        color: black;
    }

    .language.light {
        position : fixed;
        cursor: pointer;
        right: 110px;
        top: 24px;
        font-size: 24px;
        color: black;
    }

    .darklight.light {
        cursor: pointer;
        position : fixed;
        right: 65px;
        top: 27px;
        font-size: 24px;
        color: black;
    }


    @media (max-width: 768px) {

        .top.dark {
        position: fixed;
        background-color: black;
        left: 0px;
        top:  0px;
        height: 10%;
        width: 100%;
    }

    .title.dark {
        position : fixed;
        left: 20px;
        top: 28px;
        font-size: 17px;
        color: white;
    }

    .language.dark {
        cursor: pointer;
        position : fixed;
        right: 60px;
        top: 28px;
        font-size: 17px;
        color: white;
    }

    .darklight.dark {
        cursor: pointer;
        position : fixed;
        right: 15px;
        top: 24px;
        font-size: 24px;
        color: white;
    }


    .top.light {
        position: fixed;
        background-color: white;
        left: 0px;
        top:  0px;
        height: 10%;
        width: 100%;
    }

    .title.light {
        position : fixed;
        left: 20px;
        top: 28px;
        font-size: 17px;
        color: black;
    }

    .language.light {
        cursor: pointer;
        position : fixed;
        right: 60px;
        top: 28px;
        font-size: 17px;
        color: black;
    }

    .darklight.light {
        cursor: pointer;
        position : fixed;
        right: 17px;
        top: 26px;
        font-size: 24px;
        color: black;
    }

    }

    </style>
