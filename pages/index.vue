<template>
    <div>
      <v-container class="header__container" fluid>
        <div class="header__content">
          <div class="d-flex justify-space-between align-center">
            <div class="d-md-block" md3>
              <nuxt-link class="mt-3" to="/">
                <img style="cursor:pointer" height="37" width="144" src="/onestreamlogo.png" alt="onestream_logo" />
              </nuxt-link>
            </div>
            <v-flex class="d-none d-md-block" md9>
                <div class="d-flex justify-end">
                  <ul class="d-flex">
                    <li class="header-items"><a href="#features">Features</a></li>
                    <li class="header-items"><a href="#how_it_works">How It Works</a></li>
                    <li class="header-items"><a href="#pricing">Pricing</a></li>
                    <li class="header-items"><a href="#faq">FAQ</a></li>
                    <li class="header-items"><a href="#affiliate">Affiliates</a></li>
                    <li class="header-items">Sign In</li>
                    <li class="header-items">
                      <v-btn class="no-uppercase" color="#FEA74C" style="font-weight:bold; margin-top:-5px"> 
                        Sign Up Free
                      </v-btn>
                    </li>
                  </ul>
                  
                </div>
                
            </v-flex>
            <v-app-bar-nav-icon class="sm6 mt-2 d-md-none" @click.stop="drawer = !drawer" />
            <v-navigation-drawer
              v-model="drawer"
              app
              disable-resize-watcher
              color="#292B3B"
            >
              <v-list>
                <v-list-item
                  v-for="(item, i) in items"
                  :key="i"
                  :to="item.to"
                  router
                  exact
                >
                  <v-list-item-action>
                    <v-icon>{{ item.icon }}</v-icon>
                  </v-list-item-action>
                  <v-list-item-content>
                    <v-list-item-title v-text="item.title" />
                  </v-list-item-content>
                </v-list-item>
              </v-list>
            </v-navigation-drawer>
          </div> 
          <div class="line"></div>   
          <v-row class="mt-9 py-10 align-center">
            <v-col cols="12" md="6">
              <div style="width: 90%">
                <h1 class="main-title" >Live Stream Real-time & Recorded Videos</h1>
                <p class="main-subtitle mt-4">Go Live or Schedule Recorded Video Streams to 40+ Social Media Platforms at Once</p>
                <v-btn class="mt-4 no-uppercase" dark color="#4854EE" style="font-weight: 500"> 
                  Sign Up Free
                </v-btn>
              </div>
            </v-col>
            <v-col class="d-none  justify-end d-md-flex" cols="12" md="6">
              <v-avatar style="width:35vw; height:35vw;border: 1.5px solid #808687;">
                <img src="/onestreamintro.png" alt="intro_pic">
              </v-avatar>
            </v-col>
          </v-row>
        </div>    
      </v-container>
 
      <v-container fluid style="width:90%;margin:auto; overflow: hidden; height:100px;" class="d-flex justify-space-between align-center mt-1">
        <a href="https://www.facebook.com/" target="_blank"><img style="width: 98px; height:32px" src="/streams/facebook-live-logo.png" alt="fb_logo"></a>
        <a href="https://www.youtube.com/" target="_blank"><img style="width: 187px; height:125px" src="/streams/youtube.png" alt="youtube"></a>
        <a href="https://store.steampowered.com/" target="_blank"><img style="width: 229px; height:151px" src="/streams/Logo Steam.png" alt="steam"></a>
        <a href="https://vimeo.com/" target="_blank"><img style="width: 148px; height:42px" src="/streams/vimeo-logo.png" alt="vimeo"></a>
        <a href="https://www.wowza.com/" target="_blank"><img style="width: 163px; height:59px" src="/streams/wowza-logo.png" alt="wowza"></a>
      </v-container>
          
      <v-container id="features" style="height: 100vh; background-color: #4854EE" fluid>
          <div class="main__content">
            <h1 style="font-size: 40px; color:#fff">OneStream Features</h1>
            <p class="main-subtitle">Save time and effort. Focus on creating powerful videos to Stream Live.</p>
            <div class="d-flex" style="overflow-x: auto; margin-left:-50px"> 
              <v-card  data-aos="fade-left" data-aos-duration="1200" v-for="feature in features" :key="feature.header" style="border-radius:10px" min-width="350" max-width="350" max-height="270" elevation="1" class="pa-6 mt-12 ml-12">
                <div class="features d-flex align-center">
                  <img :src="feature.image" alt="img">
                  <h3 class="ml-10">{{ feature.header}}</h3>
                </div>
                <v-card-text class="mt-2">{{ feature.text}}</v-card-text>
                <v-card-actions>
                  <v-btn
                    text
                    color="#4854EE"
                    style="text-decoration: underline;text-underline-position: under"
                  >
                    Learn More
                  </v-btn>
                </v-card-actions>
              </v-card>
            </div>
            <div class="d-flex align-center justify-space-between">
              <v-btn color="#FEA74C" style="font-weight:bold;" class="mt-16 no-uppercase"> 
                Get Started For Free
              </v-btn>
              <div class="mt-16 mr-16 d-flex">
                <v-btn
                  class="mx-2"
                  elevation="0"
                  fab
                  dark
                  small
                  color="#4854EE"
                  style="border: 0.5px solid white"
                >
                  <v-icon dark>
                    mdi-arrow-left
                  </v-icon>
                </v-btn>
                <v-btn
                  class="mx-2"
                  fab
                  elevation="0"
                  dark
                  small
                  color="#4854EE"
                  style="border: 0.5px solid white"
                >
                  <v-icon dark>
                    mdi-arrow-right
                  </v-icon>
                </v-btn>
              </div>
            </div>
            
          </div>
      </v-container>

      <v-container id="how_it_works" style="height: 100vh; background-color:blue" fluid>
      </v-container>

      <v-container id="pricing" style="height: 100vh; background-color:green" fluid>
      </v-container>

      <v-container id="faq" style="height: 100vh; background-color:aqua" fluid>
      </v-container>

      <v-container id="affiliate" style="height: 100vh; background-color: grey" fluid>
      </v-container>

    </div>
</template>

<script>
import aosMixin from '~/mixins/aos'

export default {
  name: 'IndexPage',
  mixins: [aosMixin],
  data() {
    return {
      drawer: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      features: [
        {
          image: '/features/filled outline.png',
          header: 'Social Media Streaming',
          text: 'Multicast to 40+ streaming networks including Facebook Live, YouTube, Wowza Media Systems, Twitch...'
        },
        {
          image: '/features/Group.png',
          header: 'Pre-Recorded Streaming',
          text: 'Schedule your pre-recorded videos for live streaming to social media up to 60 days in advance...'
        },
        {
          image: '/features/Group2.png',
          header: 'Real Time Streaming',
          text: 'Use any streaming tool like OBS, Zoom, Wirecast, XSplit, etc and start multistreaming across social media...'
        },
        {
          image: '/features/video-player (1) 1.png',
          header: 'Embed Player',
          text: 'Embed live streams on your own website or anywhere you wish and reach wider audience with ease...'
        },
        {
          image: '/features/analytics (3) 1.png',
          header: 'Analytics & Insights',
          text: 'Gain detailed insights to your live streams performance and user engagement.'
        }
      ]
    };
  },
}
</script>

<style>
html {
  scroll-behavior: smooth;
}
* {
  font-family: 'Quicksand', sans-serif;
}
.header__container {
  background-color: #2B2D3D;
  height: 100vh;
}
.header__content {
  max-width: 90%;
  margin: auto;
  margin-top: 20px;
}
.main__content{
  margin-left: 5vw;
  margin-top: 10vh;
}
.line {
  height: 1px;
  margin-top: 8px;
  background: #464757;
}
.header-items{
  text-decoration: none;
  list-style: none;
  padding: 5px;
  line-height: 22.5px;
  margin-left: 1.5vw;
  margin-top: 5px;
  color: #fff;
  font-weight:700;
  font-size: 1.15vw;
}
.header-items a{
  text-decoration: none;
  color: #fff !important;
  font-weight:700;
  font-size: 1.15vw;
}
.main-title {
  color: #fff;
  font-size: 60px;
  font-weight: 500;
  line-height: 72px;
}
.main-subtitle {
  color: #C8C9CD;
  font-size: 20px;
  font-weight: 400;
  line-height: 32px;
}
.features img{
  width: 65px;
  height: 65px;
} 
.features h3 {
  font-size: 25px;
  color: #212121;
}
.features {
  width: 90%;
  margin: auto;
}
.no-uppercase {
     text-transform: unset !important;
}
</style>