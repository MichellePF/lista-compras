<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="drawerAbierto = !drawerAbierto"
        />
        <div class="q-pt-xl q-pb-md q-px-lg">
          <div class="text-h3">Lista de Compras:</div>
          <div class="text-subtitle1">{{ fecha }}</div>
        </div>
        <q-img src="~assets/kaisa.jpg" class="absolute-top img-fondo"></q-img>

      </q-toolbar>
    </q-header>

    <q-drawer
        v-model="drawerAbierto"
        show-if-above
        :width="300"
        :breakpoint="600"
      >
      <q-scroll-area style="height: calc(100% - 142px); margin-top: 142px; border-right: 1px solid #ddd">
        <q-list padding>
          <q-item exact to="/" clickable v-ripple>
            <q-item-section avatar>
              <q-icon name="list" />
            </q-item-section>

            <q-item-section>
              Lista
            </q-item-section>
          </q-item>

          <q-item exact to="/help" clickable v-ripple>
            <q-item-section avatar>
              <q-icon name="help" />
            </q-item-section>

            <q-item-section>
              Ayuda
            </q-item-section>
          </q-item>
        </q-list>
      </q-scroll-area>

      <q-img class="absolute-top" src="~assets/kaisa.jpg" style="height: 142px">
        <div class="absolute-bottom bg-transparent">
          <q-avatar size="56px" class="q-mb-sm">
            <img src="~assets/avatar.jpg">
          </q-avatar>
          <div class="text-weight-bold">Michelle PF</div>
          <div>@michellepf</div>
        </div>
      </q-img>
    </q-drawer>

    <q-page-container>
      <keep-alive>
        <router-view />
      </keep-alive>
    </q-page-container>
  </q-layout>
</template>

<script>
import { date } from 'quasar'

const linksData = [
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'https://quasar.dev'
  },
  {
    title: 'Github',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Discord Chat Channel',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Forum',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Twitter',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Facebook',
    caption: '@QuasarFramework',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'favorite',
    link: 'https://awesome.quasar.dev'
  }
]

export default {
  name: 'MainLayout',
  data () {
    return {
      drawerAbierto: false,
      essentialLinks: linksData
    }
  },
  computed: {
    fecha () {
      const timeStamp = Date.now()
      return date.formatDate(timeStamp, 'DD - MM - YYYY')
    }
  }
}
</script>

<style lang="scss">
  .img-fondo {
    height: 100%;
    z-index: -1;
    opacity: 0.4;
    filter: grayscale(100%);
  }
</style>
