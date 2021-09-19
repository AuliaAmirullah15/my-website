<template>
  <q-layout view="lHh Lpr lFf">
    <q-page-container>
      <router-view />
    </q-page-container>
    <div class="content-wrapper fixed-top-right q-pa-md text-white home-icon" >
        <div class="row q-gutter-lg" :class="$q.screen.lt.sm ? 'q-mr-sm': 'q-mr-lg'">
          <router-link to="/"><q-icon name="fas fa-igloo" class="col" /></router-link>
        </div>
    </div>
    <div class="gt-sm content-wrapper fixed-bottom-left q-pa-lg text-white" style="font-size: 20px;" >
        <div class="row q-gutter-lg">
          <a href="https://github.com/AuliaAmirullah15"><q-icon name="fab fa-github" class="col" /></a>
          <a href="https://www.instagram.com/auliaamir153/"><q-icon name="fab fa-instagram" class="col" /></a>
          <a href="https://www.facebook.com/aulia.amirullah.75/"><q-icon name="facebook" class="col" /></a>
          <a href="https://google.com"><q-icon name="fab fa-linkedin" class="col" /></a>
        </div>
    </div>

    <div class="content-wrapper fixed-bottom-right q-pa-lg text-white" style="font-size: 20px;" >
        <div class="row q-gutter-lg">
          <q-fab
            v-model="fabLeft"
            vertical-actions-align="right"
            color="orange"
            :label="$q.screen.lt.sm ? '' : 'More'"
            glossy
            icon="keyboard_arrow_up"
            direction="up"
            padding="sm"
          >
            <q-fab-action label-position="left" color="primary" icon="mail" label="auliaamir153@gmail.com" />
            <q-fab-action label-position="left" color="accent" icon="phone" label="+6282164588486" />
            
          </q-fab>
        </div>
    </div>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'MainLayout',

  setup () {
    return {
      fabLeft: ref(false),
      }
    }
  });
</script>

<style lang="scss">
.content-wrapper {
  width: fit-content;
}

.home-icon {
  font-size: 28px;
}

@media (max-width: 576px) {
  .home-icon {
    font-size: 20px;
  }
}
</style>
