<template>
    <div style="overflow:hidden">
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
                    <li class="header-items" style="cursor:pointer" @click="loginDialog = true">Sign In</li>
                    <li class="header-items">
                      <v-btn @click="registerDialog = true" class="no-uppercase" color="#FEA74C" style="font-weight:bold; margin-top:-5px"> 
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
              dark
              disable-resize-watcher
              color="#292B3B"
            >
              <v-list>
                <v-list-item
                  v-for="(item, i) in navItems"
                  :key="i"
                  :to="item.to"
                  
                >
                  <v-list-item-action>
                    <v-icon>{{ item.icon }}</v-icon>
                  </v-list-item-action>
                  <v-list-item-content>
                    <v-list-item-title v-text="item.title" />
                  </v-list-item-content>
                </v-list-item>
              </v-list>
              <v-btn width="87%" class="ml-4 mt-5" dark @click="loginDialog = true">Sign In</v-btn>
            </v-navigation-drawer>
          </div> 
          <div class="line"></div>   
          <v-row class="mt-9 py-10 align-center">
            <v-col cols="12" md="6">
              <div style="width: 90%">
                <h1 class="main-title" >Live Stream Real-time & Recorded Videos</h1>
                <p class="main-subtitle mt-4">Go Live or Schedule Recorded Video Streams to 40+ Social Media Platforms at Once</p>
                <v-btn @click="registerDialog = true" class="mt-4 no-uppercase" dark color="#4854EE" style="font-weight: 500"> 
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
            <div class="d-flex" style="overflow-x: hidden; margin-left:-50px"> 
              <v-slide-group
                class="slide__custom"
                show-arrows
                next-icon="mdi-arrow-right"
                prev-icon="mdi-arrow-left"
              >
              <v-slide-item
                  v-for="feature in features" :key="feature.header"
                >
              <v-card  data-aos="fade-left" data-aos-duration="1200"  style="border-radius:10px" min-width="365" max-width="365" max-height="270" elevation="1" class="pa-6 mt-7 ml-12">
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
              </v-slide-item></v-slide-group>
            </div>
  
            <div class="d-flex align-center justify-space-between">
              <v-btn @click="registerDialog = true" color="#FEA74C" style="font-weight:bold;color:#333547" class="no-uppercase"> 
                Get Started For Free
              </v-btn>
            </div>
          </div>
      </v-container>

      <v-container id="how_it_works" style="min-height: 100vh; background-color:#FFF5EB" fluid>
        <div class="mt-16">
          <div style="text-align:center">
            <h1 data-aos="fade-up" data-aos-duration="1000">How it works</h1>
            <p data-aos="fade-up" data-aos-duration="1200" style="margin-top: 17px">Video Live Streaming Simplified</p>
          </div>
          <v-tabs v-model="tab" class="mt-16" slider-color="#767CED" centered background-color="transparent">
            <v-tab class="no-uppercase" active-class="tab__active" style="border-radius: 7px 7px 0px 0px;width: 45vw;height: 54px;font-size:16px">Real Time Streaming</v-tab>
            <v-tab class="no-uppercase" active-class="tab__active" style="border-radius: 7px 7px 0px 0px;width: 45vw;height: 54px;">Pre-recorded Streaming</v-tab>
          </v-tabs>
          <v-tabs-items style="background-color:transparent" v-model="tab">
            <v-tab-item>  
              <v-row class="justify-space-between mt-14 widthmin">
                <ArrowVector />
                <v-col v-for="how in howItWorks" :key="how.header" cols="12" md="3">
                  <div data-aos="fade-down" :data-aos-duration="how.duration" class="ml-2">
                    <img :src="how.image" style="width:72px;height:72px" alt="">
                    <h2 style="color:#212331"><span style="color:#FEA74C;margin-left: -40px; margin-right: 10px">{{how.headerNo}}</span>{{how.header}}</h2>
                    <p style="color:#212331">{{how.text}}</p>
                </div>
                </v-col>
              </v-row>
            </v-tab-item>
            <v-tab-item>            
                <div class="widthmin" style="margin-bottom:6vw">
                  <h1 style="font-size:4vw; text-align:center" class="mt-6">Steps to select a video file for <br /> live streaming</h1>
                  <v-row class="mt-5 align-center">
                    <v-col class="justify-center" cols="12" md="6">
                      <p><span class="span__numbers">1</span>Either click Pre-recorded Stream on the sidebar or click New Stream button on the top and select Pre-recorded Streaming.</p>
                      <p><span class="span__numbers">2</span>Upload from your computer or choose the video stored in your cloud storage (Dropbox or Google Drive). Allowed video formats are mp4, mov, mkv.</p>
                      <p><span class="span__numbers">3</span>While the video is being uploaded, you can modify the following fields:</p>
                    </v-col>
                    <v-col cols="12" md="6" class="d-none d-md-block">
                      <img style="width:50vw" src="/image 105.png" alt="img__Description">
                    </v-col>
                  </v-row>
                </div>
            </v-tab-item>
          </v-tabs-items>
        </div>
      </v-container>

      <v-container id="" style="min-height: 70vh; background-color: #fff" fluid>
        <v-row class="widthmin align-center mt-16">
          <v-col cols="12" md="6">
            <h1 style="font-size: 5vh">Reviewed Excellent on Trustpilot</h1>
            <p style="color: #FDAC56; font-size: 3.2vh; margin-top:20px">Trusted by 65000+ Businesses</p>
            <p>We work with teams worldwide helping them live stream</p>
          </v-col>
          <v-col cols="12" md="6">
            <div class="d-flex justify-space-between">
              <img data-aos="zoom-in" data-aos-duration="800" class="business__images" src="/business/b1.png" alt="b1">
              <img data-aos="zoom-in" data-aos-duration="900" class="business__images" src="/business/b2.png" alt="b2">
              <img data-aos="zoom-in" data-aos-duration="1100" class="business__images" src="/business/b3.png" alt="b3">
              <img data-aos="zoom-in" data-aos-duration="1200" class="business__images" src="/business/b4.png" alt="b4">
            </div>
            <div class="d-flex justify-space-between mt-2">
              <img data-aos="zoom-in" data-aos-duration="1300" class="business__images" src="/business/b5.png" alt="b5">
              <img data-aos="zoom-in" data-aos-duration="1400" class="business__images" src="/business/b6.png" alt="b6">
              <img data-aos="zoom-in" data-aos-duration="1500" class="business__images" src="/business/b7.png" alt="b7">
              <img data-aos="zoom-in" data-aos-duration="1600" class="business__images" src="/business/b8.png" alt="b8">
            </div>
            <div class="d-flex justify-space-between mt-2">
              <img data-aos="zoom-in" data-aos-duration="1700" class="business__images" src="/business/b9.png" alt="b9">
              <img data-aos="zoom-in" data-aos-duration="1800" class="business__images" src="/business/b10.png" alt="b10">
              <img data-aos="zoom-in" data-aos-duration="1900" class="business__images" src="/business/b11.png" alt="b11">
              <img data-aos="zoom-in" data-aos-duration="2100" class="business__images" src="/business/b12.png" alt="b12">
            </div>
          </v-col>
        </v-row>
      </v-container>

      <div style="background-color: #515965;">
        <v-parallax src="/parallax/shutterstock_1177648855 1.png" height="380">
          <div style="text-align:center">
            <h1>OneStream mobile app also available for pre-recording streaming</h1>
            <div class="d-flex justify-center mt-7">
              <img src="/parallax/apple.png" alt="">
              <img src="/parallax/google.png" alt="">
            </div>
          </div>
        </v-parallax>
      </div>

      <v-container class="d-none d-md-block" id="pricing" style="min-height: 100vh; background-color: #fff" fluid>
        <div class="mt-16" style="text-align:center">
          <h1 data-aos="fade-up" data-aos-duration="1000">Plans & Pricing</h1>
          <p data-aos="fade-up" data-aos-duration="1200" style="margin-top: 17px">We do not nickel and dime you for features like transcoding or processing</p>
        </div>
        <v-row class="mt-14 mb-8 widthmin">
          <v-col data-aos="fade-right" data-aos-duration="1200" class="pricing__col" cols="3">
            <h3>FREE</h3>
            <p class="mt-4">No credit card required!</p>
            <div class="pricing mt-4">
              <p v-for="plan in freePlan" :key="plan"><span><v-icon>mdi-check-circle-outline</v-icon></span>{{plan}}</p>
            </div>
            <h3 class="mt-7">$  0 / month</h3>
            <v-btn class="no-uppercase mt-4" dark color="#4854EE">Try For Free</v-btn>
          </v-col>
          <v-col data-aos="fade-right" data-aos-duration="1200" class="pricing__col" cols="3">
            <h3>BASIC</h3>
            <p class="mt-4">Billed annually</p>
            <div class="pricing mt-4">
              <p v-for="plan in freePlan" :key="plan"><span><v-icon>mdi-check-circle-outline</v-icon></span>{{plan}}</p>
            </div>
            <h3 class="mt-7">$  8 / month</h3>
            <v-btn class="no-uppercase mt-4" dark color="#4854EE">Get Started</v-btn>
          </v-col>
          <v-col data-aos="fade-right" data-aos-duration="1200" class="pricing__col" cols="3">
            <h3>STANDARD</h3>
            <p class="mt-4">Billed annually</p>
            <div class="pricing mt-4">
              <p v-for="plan in freePlan" :key="plan"><span><v-icon>mdi-check-circle-outline</v-icon></span>{{plan}}</p>
            </div>
            <h3 class="mt-7">$  32 / month</h3>
            <v-btn class="no-uppercase mt-4" dark color="#4854EE">Get Started</v-btn>
          </v-col>
          <v-col data-aos="fade-right" data-aos-duration="1200" class="pricing__col" cols="3">
            <h3>PROFESSIONAL</h3>
            <p class="mt-4">PROFESSIONAL</p>
            <div class="pricing mt-4">
              <p v-for="plan in freePlan" :key="plan"><span><v-icon>mdi-check-circle-outline</v-icon></span>{{plan}}</p>
            </div>
            <h3 class="mt-7">$  74 / month</h3>
            <v-btn class="no-uppercase mt-4" dark color="#4854EE">Get Started</v-btn>
          </v-col>
        </v-row>
      </v-container>

      <v-container id="faq" style="min-height: 80vh; background-color: #FFF5EB" fluid>
        <div class="widthmin mb-16">
          <v-row class="mt-16 mx-1 justify-space-between">
            <div>
              <h1>FAQ,s</h1>
              <p>Common questions and answers</p>
            </div>
            <div>
              <h3 style="color: #535EEE">Cant Find a Suitable Awnser?</h3>
              <p>Ask our Support team</p>
            </div>
          </v-row>
          <v-expansion-panels multiple class="mt-4">
            <v-expansion-panel class="mt-6" active-class="expansion__style" v-for="item in expansionItems" :key="item.header">
              <v-expansion-panel-header>{{item.header}}</v-expansion-panel-header>
              <v-expansion-panel-content style="padding:10px">{{item.answer}}</v-expansion-panel-content>
            </v-expansion-panel>
          </v-expansion-panels> 
        </div>
      </v-container>

      <div style="background-color: #242635;">
        <v-parallax src="/parallax/shutterstock_1487351807 1.png" height="250">
          <div style="text-align:center">
            <h1>Signup your FREE Account</h1>
            <v-btn @click="registerDialog = true" dark class="no-uppercase mt-8" color="#4854EE" style="font-weight:bold;"> 
              Sign Up Free
            </v-btn>
          </div>
        </v-parallax>
      </div>

      <v-container style="min-height: 100vh; background-color: #fff" fluid>
        <div class="mt-16" style="text-align:center">
          <h1 data-aos="fade-up" data-aos-duration="1000">Not convinced yet?</h1>
          <p data-aos="fade-up" data-aos-duration="1200" style="margin-top: 17px">Check out these awesome features</p>
        </div>
        <div class="widthmin">
          <v-row class="mt-15 align-center">
            <v-col class="justify-center" cols="12" md="6">
              <div class="mt-4" data-aos="fade-up" data-aos-duration="1200">
                <img class="feature__image" src="/features/analytics (3) 1.png" alt="feature_description">
                <h3 class="ml-16">Analytics & Insights</h3>
                <p class="ml-16">Gain detailed insights to your live streams performance and user engagement.</p>
              </div>
              <div class="mt-12" data-aos="fade-up" data-aos-duration="1200">
                <img class="feature__image" src="/features/data (4) 1.png" alt="feature_description">
                <h3 class="ml-16">OneStream Storage</h3>
                <p class="ml-16">Save your videos and use them to reschedule your streams. Save your time and bandwidth.</p>
              </div>
              <div class="mt-12" data-aos="fade-up" data-aos-duration="1200">
                <img class="feature__image" src="/features/360-video (1) 1.png" alt="feature_description">
                <h3 class="ml-16">360° Videos Support</h3>
                <p class="ml-16">Go live even with recorded 180° or 360° videos. Engage your viewers like never before.</p>
              </div>
            </v-col>
            <v-col cols="12" md="6" class="d-none d-md-block">
              <img style="width:45vw" src="/features/image 17.png" alt="img__Description">
            </v-col>
          </v-row>
        </div>
      </v-container>

      <div id="affiliate" style="background-color: #4652EC;">
        <v-parallax src="/parallax/shutterstock_1177648855 2.png" height="380">
          <div style="text-align:center">
            <h1>$ Refferal Program</h1>
            <p>OneStream's affiliate program shares 55% revenue for every paid subscriber referred by you.</p>
            <v-btn dark class="no-uppercase mt-7" color="#FEA74C" style="font-weight:bold;"> 
              Become An Affiliate
            </v-btn>
          </div>
        </v-parallax>
      </div>

      <v-container style="min-height: 50vh; background-color: #35374A" fluid>
        <v-row style="color: white;" class="widthmin mt-10" >
          <v-col cols="12" md="5">
            <div class="footer__items" style="width:80%">
              <img style="cursor:pointer" height="37" width="144" src="/onestreamlogo.png" alt="onestream_logo" /> 
              <p class="mt-5">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy</p>
              <div class="d-flex mt-10">
                <a href="#features">Features</a>
                <a class="ml-5" href="#pricing">Pricing</a>
                <a class="ml-5" href="#faq">FAQ</a>
              </div>
            </div>
          </v-col>
          <v-col cols="6" md="2">
            <h3 style="color: #E5994C">LEARN MORE</h3>
            <p class="mt-4">Pricing</p>
            <p>Features<p>
            <p>Register</p>
          </v-col>
          <v-col cols="6" md="2">
            <h3 style="color: #E5994C">LEARN MORE</h3>
            <p class="mt-4">Live Chat</p>
            <p>Helpdesk<p>
            <p>Blog</p>
            <p>Affiliates</p>
          </v-col>
          <v-col cols="12" md="3">
            <h3 style="color: #E5994C">CONTACT US</h3>
            <p class="mt-4">Addis Center Tower
            <br> Addis 1, 02100
            <br> Addis Ababa, Ethiopia</p>
          </v-col>
        </v-row>
        <hr class="mt-10" style="color: #3A3C4F; width:90%;margin:auto; opacity:10%">
        <v-row class="widthmin justify-space-between align-center">
          <p style="color:#A8A9B1" class="mt-5">&copy; {{ new Date().getFullYear() }} Developed by Samuel L. Bekele</p>
          <div class="d-flex socials mt-2"> 
            <img style="width: 10px; height: 20px;" src="/social/XMLID 835.png" alt="fb">
            <img style="width: 22px; height: 19px;" src="/social/XMLID 827.png" alt="twitter">
            <img style="width: 17px; height: 17px;" src="/social/insta.png" alt="insta">
            <img style="width: 23px; height: 17px;" src="/social/Subtract.png" alt="insta">
          </div>
        </v-row>
      </v-container>
      <v-dialog
        v-model="loginDialog"
        width="450"
      >
      <v-card class="px-12 py-8">
        <h2>Login To OneStream</h2>
        <p class="mt-2">Please enter email & password to login</p>
        <p class="mt-9">Email Address</p>
        <v-text-field
            placeholder="please enter your email adderess"
            outlined
            background-color="#F4F5F8"
        ></v-text-field>
        <p>Password</p>
        <v-text-field
        type="password"
            placeholder="*************"
            outlined
            background-color="#F4F5F8"
        ></v-text-field>
        <div style="margin-top:-15px" class="d-flex align-center justify-space-between ">
          <v-checkbox
            :label="`Stay Signed In`"
          ></v-checkbox>
          <p class="mt-2" style="cursor: pointer;color: #FDB261">Forgot password?</p>
        </div>
        <v-btn dark class="no-uppercase mt-2" style="width: 100%;" color="#4854EE">Sign In</v-btn>
        <hr class="mt-8" style="width: 90%; margin:auto; color: #F0F0F0; opacity: 50%">
        <div class="mt-4">
          <p style="text-align:center"> Don't have an account yet?  <span @click="registerDialog = true; loginDialog = false; " style="cursor: pointer; color: #FDB261">Sign Up</span></p>
        </div>
        <div class="d-flex justify-space-around mt-6">
          <img class="log__social" src="/social/facebook (6) 6.png" alt="fb">
          <img class="log__social"  src="/social/google (1) 1.png" alt="fb">
          <img class="log__social"  src="/social/apple (1) 1.png" alt="fb">
        </div>
      </v-card>
      </v-dialog>

      <v-dialog
        v-model="registerDialog"
        width="450"
      >
      <v-card class="px-12 py-8">
        <h2>Sign Up To OneStream</h2>
        <p class="mt-2">Register new OneStream account</p>
        <p class="mt-9">Name</p>
        <v-text-field
            placeholder="Samuel bekele"
            outlined
            background-color="#F4F5F8"
        ></v-text-field>
        <p>Email Address</p>
        <v-text-field 
            placeholder="samuellegese61@gmail.com"
            outlined
            background-color="#F4F5F8"
        ></v-text-field>
        <p>Password</p>
        <v-text-field
        type="password"
            placeholder="*************"
            outlined
            background-color="#F4F5F8"
        ></v-text-field>
        <div class="mt-2">  
          <p style="text-align:center"> I agree to OneStream   <span style="cursor: pointer; color: #FDB261">Terms</span> & <span style="cursor: pointer; color: #FDB261">Privacy Policy</span></p>
        </div>
        <v-btn dark class="no-uppercase mt-2" style="width: 100%;" color="#4854EE">Create Account</v-btn>
        <hr class="mt-8" style="width: 90%; margin:auto; color: #F0F0F0; opacity: 50%">
        <div class="mt-6"> 
          <p style="text-align:center"> Already have an account? <span @click="registerDialog = false; loginDialog = true; " style="cursor: pointer; color: #FDB261">Sign In</span></p>
        </div>
        <div class="d-flex justify-space-around mt-6">
          <img class="log__social" src="/social/facebook (6) 6.png" alt="fb">
          <img class="log__social"  src="/social/google (1) 1.png" alt="fb">
          <img class="log__social"  src="/social/apple (1) 1.png" alt="fb">
        </div>
      </v-card>
      </v-dialog>

    </div>
</template>

<script>
import aosMixin from '~/mixins/aos'
import ArrowVector from '../components/ArrowVector.vue'
export default {
  name: 'IndexPage',
  mixins: [aosMixin],
  components: {
    ArrowVector
  },
  data() {
    return {
      loginDialog: false,
      registerDialog: false,
      drawer: false,
      tab: null,
      expansionItems: [
        {
          header: '01. What is OneStream?',
          answer: 'OneStream is a cloud based service to schedule & live stream pre-recorded videos as well as real-time streaming to 40+ social media platforms including Facebook Live, YouTube, Instagram, Twitch or any Custom RTMP Streaming Destination.'
        },
        {
          header: '02. Who can use OneStream?',
          answer: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
        },
        {
          header: '03. Video formats & qualities?',
          answer: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
        },
        {
          header: '04. More Questions?',
          answer: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
        },
      ],
      freePlan: [
        'Unlimited Live Streaming',
        'Pre-recorded Streaming',
       ' No Real-time Streaming',
        'No Multicasting',
        '1 Queued stream at a time',
        'No Playlist Streaming',
        '5 min max / recorded stream',
        '1 Social account',
        '5 GB max video file size',
        '5 min Camera recording',
        '5 min Screen capturing'
      ],
      howItWorks: [
        {
          image: '/features/Group.png',
          header: 'Get Streaming Settings (RTMP)',
          headerNo: '01',
          text: 'Copy your Server URL and Stream Key from OneStream dashboard.',
          duration: '1200'
        },
        {
          image: '/features/Group.png',
          header: 'Configure Streaming Tool',
          headerNo: '02',
          text: 'Setup external streaming software like OBS, Zoom, Wirecast, XSplit, etc. and start sending stream to OneStream servers.',
          duration: '1700'
        },
        {
          image: '/features/Group.png',
          header: 'Start Multicasting',
          headerNo: '03',
          text: 'Select streaming destinations. Choose multiple destination streaming platforms where you wish to multistream your incoming stream.',
          duration: '2400'
        },
      ],
      navItems: [
        {
          icon: 'mdi-apps',
          title: 'OneStream',
          to: '/'
        },
        {
          icon: 'mdi-star-circle-outline',
          title: 'Features',
          to: '#features'
        },
        {
          icon: 'mdi-application-cog-outline',
          title: 'How It Works',
          to: '#how_it_works'
        },
        {
          icon: 'mdi-frequently-asked-questions',
          title: 'FAQ',
          to: '#faq'
        },
        {
          icon: 'mdi-account-group',
          title: 'AffiliateS',
          to: '#affiliate'
        },
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
.widthmin{
  width: 90%;
  margin: auto;
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
.footer__items a{
  color: #E4994B !important;
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
.slide__custom {
  height: 400px !important;
  padding: 0 !important;
}
.slide__custom  .v-slide-group__next{
  padding: 0 !important;
  margin-right: -55px !important;
}
.slide__custom  .v-slide-group__prev{
  padding: 0px !important;
  margin-left: -50px !important;
}
.slide__custom  .v-slide-group__next .v-icon  {
    color: white !important;
    border: 1px solid white !important;
    padding: 10px !important;
    border-radius: 50% !important;
    background-color: transparent !important;
    position: absolute !important;
    top: 340px !important; 
    right: 80px !important; 
    z-index: 100000;
    margin-left: 20px !important;
    
}
.slide__custom  .v-slide-group__prev .v-icon  {
    color: white !important;
    border: 1px solid white !important;
    padding: 10px !important;
    border-radius: 50% !important;
    background-color: transparent !important;
    position: absolute !important;
    top: 340px !important; 
    right: 150px !important; 
    z-index: 100000;

}
.tab__active {
  background-color: #4854EE;
  color: white !important;
}
.svg__vector {
  position: absolute;
  opacity: 50%;
  max-width: 90%;
}
.span__numbers {
  background-color: #FEA74C;
  padding: 12px;
  border-radius: 50%;
  margin-left: -40px; 
  margin-right: 10px
}
.business__images {
  width: 104px;
  height: 104px;
}
.pricing span {
  margin-right: 10px;
}
.pricing i{
  color: #FDA74B !important;
}
.pricing p{
  font-size: 14px;
}
.pricing__col:not(:first-of-type){
  border-left: 1px solid #eeeeee;
}
.expansion__style .v-expansion-panel-header{
  background-color: #4854EE;
  color: white;
}
.feature__image {
  float: left;
  width: 60px;  
  height: 60px;
  margin-right: 15px;
  padding: 10px;
  background: #FDA74B;
  border-radius: 10px;
}
.socials :not(:first-child){
  margin-left: 30px;
}
.log__social{
  width: 40px;
  height: 40px;
  cursor: pointer;
}
@media only screen and (max-width: 800px) {
  .span__numbers {
    padding: 8px;
    margin-left: -10px; 
    margin-right: 5px;
  }
  .business__images {
    width: 70px;
    height: 70px;
  }
}
</style>