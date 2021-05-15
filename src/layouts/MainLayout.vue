<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated >
      <q-toolbar class="bg-blue-grey-10">
        <q-btn
          flat
          dense
          round
          icon="headphones"
          aria-label="Menu"
          @click="leftDrawerOpen =! leftDrawerOpen"
        />

        <q-toolbar-title>
          Sound on Lofi
        </q-toolbar-title>

        <div>
          <strong>Music for Life</strong>
        </div>
        
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      content-class="bg-blue-grey-10"
    >
      <q-list>
        <q-item-label
          header
          class="text-white"
        >
          <strong>Navegation</strong>  
        </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
          class="text-white"
        />
      </q-list>
    </q-drawer>

    <q-carousel
      animated
      v-model="slide"
      arrows
      navigation
      infinite
      style="height: 68vh"
    >
      <q-carousel-slide :name="1" img-src="https://wallpapercave.com/wp/wp6424372.jpg" />
      <q-carousel-slide :name="2" img-src="https://wallpapercave.com/wp/wp3826695.jpg" />
      <q-carousel-slide :name="3" img-src="https://wallpaperboat.com/wp-content/uploads/2020/12/18/64126/future-21.jpg" />
      <q-carousel-slide :name="4" img-src="https://wallpaperforu.com/wp-content/uploads/2020/07/car-wallpaper-2007261221322.jpg" />
    </q-carousel> 

    <q-page-container class="q-pt-none bg-dark">
      <router-view />
    </q-page-container>    
    
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksData = [
  {
    title:'Spotify',
    icon: 'headphones',
    link:'https://www.spotify.com'
  },

  {
    title: 'YouTube Channel',
    icon: 'smart_display',
    link: 'https://youtube.com'
  },

  {
    title: 'Instagram',
    icon: 'local_see',
    link: 'https://instagram.com'
  },

  {
    title: 'Facebook',
    icon: 'public',
    link: 'https://facebook.com'
  },
];

export default {
  name: 'MainLayout',
  components: { EssentialLink },
  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData,
      slide:1
    }
  }
}
</script>

<style>
  *{
    padding:0;
    margin:0;
    -webkit-box-sizing: border-box;
            box-sizing: border-box;
  }
</style>
