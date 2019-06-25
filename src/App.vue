<template>
  <div id="app">
    <h1>Mon cv</h1>
        <div class="element-jake" id="jake">
            
            <a href="#"><img @click="adventure" src="https://img.icons8.com/color/100/000000/jake.png"></a>
            <span class="element-jake-hide">{{ randomPhrase }}</span>
        </div>
        <div class="container">
            <div class="container-infos-profil">
                <br>
                <div class="photo-profile">
                    <img src="./assets/img/profil_cat.jpg" alt="cat-profil">
                </div>
                <div class="infos-infos">
                    <h3>Infos</h3>
                    <p>Developpeur web junior FRONT</p>
                </div>
                <div class="contact-infos" id="profilContact">
                    <h3>Contact</h3>
                    <p>Phone : {{ phone }}</p>
                    <p>Mail : {{ mail }}</p>
                </div>
                <div class="outil-infos">
                    <h3>Stuff</h3>
                    <p>Html/Css, Javascript, scss, Vuejs</p>
                </div>
                <br>
                <div class="lien-click">
                    <h3>Liens</h3>
                    <br>
                    <a href="https://www.instagram.com/"><img src="https://img.icons8.com/color/50/000000/treasure-chest.png"></a>
                    <a href="https://www.youtube.com/"><img src="https://img.icons8.com/color/50/000000/sword.png"></a>
                    <a href="http://www.jeuxvideo.com/"><img src="https://img.icons8.com/color/48/000000/kawaii-coffee.png"></a>
                </div>
            </div>
            <div class="container-infos-xp">
                    <Info title="Expérience" :infos="experience" />
                    <Info title="Éducation" :infos="education" />
                    <Info title="Loisirs" :infos="loisir" />
            </div>
        </div>
  </div>
</template>

<script>
import Info from './components/Info.vue'
import './assets/scss/index.scss';

export default {
  name: 'app',
  components: {
    Info
  },
  data() {
    return {
      phrase: ['Don\'t touch me anymore', 
                'TU tu TU tu TU tu tu TU',
                'Look at my poweEeeEer', 
                'Oh my doggyDog ?!'
              ],
        randomPhrase: '',
        phone: '06.79.86.38.05',
        mail: 'mleutard@gmail.com',
        experience: [
          { name: 'Stage de Mai 2019/juillet 2019 : ADFAB -> developpeur web FRONT junior'}
        ],
        education: [
          { name: 'Ifocop -> formation developpeur web junior 2017' },
          { name: 'OpenClassRooms -> formation developpeur web junior 2018/2019' }
        ],
        loisir: [
          { name: 'Theatre' },
          { name: 'Jeux videos' },
          { name: 'Skateboard' }
        ]
    }
  },
  methods: {
      adventure () {
          let crea = document.querySelector('.element-jake span');

          if (crea.classList.contains('element-jake-hide')) {
              crea.classList.remove('element-jake-hide');
              this.speakJake();
          } else {
              crea.classList.add('element-jake-hide');
          }
      },

      speakJake () {
          const index = Math.floor(Math.random() * this.phrase.length);
          this.randomPhrase = this.phrase[index];
      }
  }
}
</script>
