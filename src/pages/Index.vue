<template>
  <q-page class="flex flex-center">
     <q-carousel
      v-model="slide"
      vertical
      transition-prev="slide-down"
      transition-next="slide-up"
      swipeable
      animated
      control-color="white"
      padding
      arrows
      height="100vh"
      style="width: 100%"
      class="bg-grey-1 text-white shadow-1 rounded-borders"
    >
      <q-carousel-slide name="profile" class="column no-wrap flex-center">
        <div class="q-mt-md text-center">
          <q-avatar size="150px">
            <img src="~assets/fotokuu.jpg" style="object-fit: cover">
          </q-avatar>
          <p class="text-name no-margin text-montserrat">Aulia Amirullah</p>
          <p class="text-desc no-margin">24 Years Old</p>
          <p class="text-desc no-margin">Software Developer</p>
          <p class="text-desc no-margin"><span><q-icon name="fas fa-map-marker-alt" /></span> Medan, Indonesia</p>
          <div class="row q-gutter-md q-pa-sm">
            <q-chip :size="$q.screen.lt.sm ? 'sm' : 'lg'" color="red" text-color="white">
              Python
            </q-chip>
            <q-chip :size="$q.screen.lt.sm ? 'sm' : 'lg'" color="primary" text-color="white">
              Javascript
            </q-chip>
            <q-chip :size="$q.screen.lt.sm ? 'sm' : 'lg'" color="orange" text-color="white">
              PHP
            </q-chip>
          </div>
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="projects" class="column no-wrap flex-center">
        <div class="q-pa-xs" style="height: 90%;">
          <div class="row justify-center q-gutter-xs">
            <q-intersection
              v-for="(project, index) in projects"
              :key="index"
              transition="scale"
              class="example-item"
            >
              <q-card class="q-ma-sm text-black text-sans-serif">
                <img src="~assets/suci-kurnia.png" style="height: 150px;" v-if="index === 0"/>
                <img src="~assets/beauty-spa.png" style="height: 150px;" v-if="index === 1"/>
                <img src="~assets/market-place-coach.png" style="height: 150px;" v-if="index === 2"/>
                <img src="~assets/qinventory.png" style="height: 150px;" v-if="index === 3"/>
                <img src="~assets/backend-inventory.png" style="height: 150px;" v-if="index === 4"/>
                <img src="~assets/Battleship.png" style="height: 150px;" v-if="index === 5"/>
                <img src="~assets/simta.png" style="height: 150px;" v-if="index === 6"/>
                <img src="~assets/simia.png" style="height: 150px;" v-if="index === 7"/>
                <img src="~assets/simpbb.png" style="height: 150px;" v-if="index === 8"/>
                <img src="~assets/my-profile.png" style="height: 150px;" v-if="index === 9 "/>

                <!-- <q-img :src="project.image" style="height: 150px;" /> -->

                <q-card-section class="text-center">
                  <div class="text-bold">{{ project.name }}</div>
                  <div style="height: 100px">
                    <div class="row q-py-sm q-gutter-sm">
                    <q-badge v-for="(badge, key) in project.badges" :key="key" :color="badge.color">
                      {{ badge.name }}
                    </q-badge>
                    </div>
                  </div>
                  <div class="row flex-center q-gutter-sm">
                    <a :href="project.github"><q-btn color="primary" icon="fab fa-github" :label="project.status == 'private' ? 'private' : ''" size="sm" :disable="project.status == 'private'"/></a>
                    <a :href="project.website"><q-btn color="primary" icon="link" size="sm" /></a>
                  </div>
                  <q-badge class="q-mt-sm" color="orange" v-if="project.website === '#'">
                      {{ project.category }}
                    </q-badge>
                </q-card-section>
              </q-card>
            </q-intersection>
          </div>
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="layers" class="column no-wrap flex-center">
        <q-icon name="layers" size="56px" />
        <div class="q-mt-md text-center">
          {{ lorem }}
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="map" class="column no-wrap flex-center">
        <q-icon name="terrain" size="56px" />
        <div class="q-mt-md text-center">
          {{ lorem }}
        </div>
      </q-carousel-slide>
    </q-carousel>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue';
import { ref } from 'vue'

export default defineComponent({
  name: 'PageIndex',
   setup () {
    return {
      slide: ref('profile'),
      projects: [
        {
          image: 'https://localhost:8091/img/suci-kurnia.png',
          name: 'Suci Kurnia (E-Commerce)',
          badges: [
            {
              color: 'primary',
              name: 'Bootstrap 5',
            },
            {
              color: 'orange',
              name: 'HTML5',
            },
            {
              color: 'teal',
              name: 'CSS3',
            },
            {
              color: 'red',
              name: 'Vanilla Javascript',
            },
            {
              color: 'secondary',
              name: 'Vuejs 3',
            },
            {
              color: 'blue',
              name: 'Jquery',
            },
            {
              color: 'accent',
              name: 'SASS'
            }
          ],
          github: 'https://github.com/AuliaAmirullah15/suci-kurnia',
          website: 'https://suci-kurnia.netlify.app/',
          status: 'public',
        },
        {
          image: 'http://localhost:8093/img/beauty-spa.png',
          name: 'AHA Beauty & Spa',
          badges: [
            {
              color: 'primary',
              name: 'Bootstrap 4',
            },
            {
              color: 'orange',
              name: 'HTML5',
            },
            {
              color: 'teal',
              name: 'CSS3',
            },
            {
              color: 'red',
              name: 'Vanilla Javascript',
            },
            {
              color: 'blue',
              name: 'Jquery',
            },
          ],
          github: 'https://github.com/AuliaAmirullah15/spa',
          website: 'https://aha-beauty-products.netlify.app',
          status: 'public',
        },
        {
          image: 'http://localhost:8093/img/market-place-coach.png',
          name: 'Coach Market Place',
          badges: [
            {
              color: 'orange',
              name: 'HTML5',
            },
            {
              color: 'teal',
              name: 'CSS3',
            },
            {
              color: 'secondary',
              name: 'Vuejs 3',
            },
          ],
          github: 'https://github.com/AuliaAmirullah15/market-place',
          website: 'https://market-place-asas.netlify.app',
          status: 'public',
        },
        {
          image: 'http://localhost:8093/img/qinventory.png',
          name: 'Inventory Frontend - Activ8te',
          badges: [
            {
              color: 'orange',
              name: 'HTML5',
            },
            {
              color: 'teal',
              name: 'CSS3',
            },
            {
              color: 'secondary',
              name: 'Vuejs 3',
            },
            {
              color: 'green',
              name: 'Quasar 2.0.3',
            },
            {
              color: 'accent',
              name: 'SASS'
            }
          ],
          github: '',
          website: 'https://myinventorys.netlify.app/#/',
          status: 'private',
        },
        {
          image: 'http://localhost:8093/img/backend-inventory.png',
          name: 'Inventory Backend- Activ8te',
          badges: [
            {
              color: 'orange',
              name: 'HTML',
            },
            {
              color: 'teal',
              name: 'CSS',
            },
            {
              color: 'secondary',
              name: 'Vuejs 2',
            },
            {
              color: 'green',
              name: 'Quasar 1.5.3',
            },
            {
              color: 'accent',
              name: 'SASS'
            }
          ],
          github: '',
          website: 'https://dev.activate.vi9e.com/qinventory/#/login',
          status: 'private',
        },
        {
          image: 'http://localhost:8093/img/Battleship.png',
          name: 'Battleship',
          badges: [
            {
              color: 'orange',
              name: 'HTML',
            },
            {
              color: 'teal',
              name: 'CSS',
            },
            {
              color: 'secondary',
              name: 'Vuejs 3',
            },
          ],
          github: 'https://github.com/AuliaAmirullah15/battleship',
          website: 'https://battleship-wargame.netlify.app/',
          status: 'public',
        },
        {
          image: 'http://localhost:8093/img/simta.png',
          name: 'Bachelor Thesis Portal',
          badges: [
            {
              color: 'accent',
              name: 'Codeigniter',
            },
            {
              color: 'orange',
              name: 'HTML',
            },
            {
              color: 'teal',
              name: 'CSS',
            },
            {
              color: 'red',
              name: 'Vanilla Javascript',
            },
            {
              color: 'blue',
              name: 'Jquery',
            },
            {
              color: 'accent',
              name: 'PHP',
            },
          ],
          github: 'https://github.com/AuliaAmirullah15/simta',
          website: '#',
          status: 'public',
          category: "Being Deployed..."
        },
        {
          image: 'http://localhost:8093/img/simia.png',
          name: 'Academic Report Portal',
          badges: [
            {
              color: 'accent',
              name: 'Codeigniter',
            },
            {
              color: 'orange',
              name: 'HTML',
            },
            {
              color: 'teal',
              name: 'CSS',
            },
            {
              color: 'red',
              name: 'Vanilla Javascript',
            },
            {
              color: 'blue',
              name: 'Jquery',
            },
            {
              color: 'accent',
              name: 'PHP',
            },
          ],
          github: 'https://github.com/AuliaAmirullah15/simia',
          website: '#',
          status: 'public',
          category: "Being Deployed..."
        },
        {
          image: 'http://localhost:8093/img/simpbb.png',
          name: 'Assets and Finance System',
          badges: [
            {
              color: 'accent',
              name: 'Codeigniter',
            },
            {
              color: 'orange',
              name: 'HTML',
            },
            {
              color: 'teal',
              name: 'CSS',
            },
            {
              color: 'red',
              name: 'Vanilla Javascript',
            },
            {
              color: 'blue',
              name: 'Jquery',
            },
            {
              color: 'accent',
              name: 'PHP',
            },
          ],
          github: 'https://github.com/AuliaAmirullah15/simpbb',
          website: '#',
          status: 'public',
          category: "Being Deployed..."
        },
        {
          image: 'http://localhost:8093/img/my-profile.png',
          name: 'My Profile',
          badges: [
            {
              color: 'orange',
              name: 'HTML5',
            },
            {
              color: 'teal',
              name: 'CSS3',
            },
            {
              color: 'secondary',
              name: 'Vuejs 3',
            },
            {
              color: 'green',
              name: 'Quasar 2.1.0',
            },
            {
              color: 'accent',
              name: 'SASS'
            }
          ],
          github: 'https://github.com/AuliaAmirullah15/my-website',
          website: 'https://auliaamirullah15.netlify.app',
          status: 'public',
        },
      ],
      lorem: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Itaque voluptatem totam, architecto cupiditate officia rerum, error dignissimos praesentium libero ab nemo.'
    }
  }
})
</script>

<style scoped lang="scss">
.bg-grey-1 {
  background-image: linear-gradient(to right top, #002f74, #234489, #3b5a9e, #5270b4, #6888ca, #679adb, #67adea, #69bff8, #52cffe, #41dfff, #46eefa, #5ffbf1) !important;
}

.example-item {
  height: 360px;
  width: 290px;
}

.project-wrapper {
  height: 70%;
  background: black;
}
</style>