<template>
    <div id="app">
        <div class="main_view">
            <div class="container">
                <div class="row">
                    <div class="col-lg-6" id="left">
                        <h1> <strong>Social Analytics </strong></h1>
                        <p>Social Analytics is a simple web tool that uses the Twitter API to collect public user data and then combines sentiment and categorical analysis to give the user a sense of what their data says about them as a person.</p>
                        <button class="cp_btn" v-scroll-to="'#twitter_account'"> Try Now </button>
                    </div>
                    <div class="col-lg-2" id="right"></div>
                    <div class="col-lg-4" id="right"><Signup/></div>
                </div>
            </div>
        </div>

        <div id="twitter_account">
            <Language-API/>
        </div>
        <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->
    </div>
</template>

<script>
import Vue from 'vue'
import axios from 'axios'
import twit from 'twit'
import HelloWorld from './components/HelloWorld.vue'
import LanguageAPI from './components/LanguageAPI.vue'
import GetTweet from './components/GetTweet.vue'
import tweet from './components/tweet.js'
import Signup from './components/Signup.vue'
// bootstrap
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import BootstrapVue from 'bootstrap-vue'
//scroll page
import vueScrollto from 'vue-scrollto'

Vue.use(BootstrapVue)
Vue.use(vueScrollto)

Vue.prototype.$http = axios;
Vue.prototype.$twit = twit;
Vue.prototype.$tweet = tweet;

export default {
    name: 'app',
    components: {
        Signup, 
    }
}
Vue.component("Hello-World", HelloWorld);


Vue.component("Language-API", LanguageAPI);
Vue.component("Get-Tweet", GetTweet);
</script>
<style>
body{
    background-color: white;
}

h1{
    font-size: 48px;
}

#app {
  font-family: 'Helvetica', Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #526F75;
  font-size: 20px;
}

.main_view{
    width: 100%;
    background: linear-gradient(#4FC3F7, #81D4FA);
    color: white;
    padding-top: 180px;
    padding-bottom: 180px;
}

#twitter_account{
    width: 100%;
    background-color: #03A9F4;
    padding-top: 100px;
    padding-bottom: 100px;
    color: white;
}

/*
Color code
https://htmlcolorcodes.com/color-chart/material-design-color-chart/
*/

</style>