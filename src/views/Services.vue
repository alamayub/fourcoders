<template>
  <div class="services__div white">
    <div class="text__banner" data-aos="zoom-in">
      <div class="text__banner__content text-h4 text-md-h3 text-lg-h2">
        <div style="line-height: 1;">FourCoders</div>
        <span class="mt-3 mt-md-5 text-h6 text-md-h5">Services</span>
      </div>
    </div>
    <div style="background-color: rgb(128 128 128 / 4%);" class="py-10 py-sm-12 py-md-14 py-lg-16">
      <v-container>
        <p style="text-align: start !important; font-size: 14px !important;">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ipsam minima voluptate quos, fuga atque accusantium natus neque nisi quasi excepturi, alias ad saepe nulla consequuntur quibusdam assumenda pariatur maiores aut. Lorem ipsum dolor, sit amet consectetur adipisicing elit. Hic commodi iste nostrum, fugiat repudiandae quod reiciendis iusto quam repellat aut? Perferendis quam accusamus laudantium, dolorum natus officiis perspiciatis sit id?</p>
      </v-container>
    </div>
    <v-container class="py-10 py-sm-12 py-md-14 py-lg-16">
      <div class="headline mb-4" data-aos="fade-up" style="line-height: 1;">Our Services</div>
      <div class="services__container">
        <div class="services__container__item px-3 py-6 px-sm-4 py-sm-8 px-md-5 py-md-10 px-lg-6 py-lg-12" v-for="(item, i) in  services" :key="i" data-aos="zoom-in">
          <v-icon class="pa-4" style="background: linear-gradient(90deg, rgba(243,108,39,1) 0%, rgba(156,39,176,1) 100%);  border-radius: 50%;" color="white">{{ item.icon }}</v-icon>
          <div class="mb-1 mt-4 text-capitalize" style="line-height: 1.2; font-weight: bold; display: block; font-size: 20px;">{{ item.name }}</div>
          <p class="text-center">There are many variations of passages of lorem Ipsum available but the new majority have suffered.</p>
        </div>
      </div>
    </v-container>
    <div style="background-color: rgb(128 128 128 / 4%);" class="py-10 py-sm-12 py-md-14 py-lg-16">
      <v-container>
        <div class="mb-6 text-center" data-aos="fade-up">
          <div class="headline">What Do We Offer</div>
          <p style="text-align: center !important;">For us, customer satisfaction comes first. We provide latest methods and tehnologies to fulfill our customers criteria.</p>
        </div>
        <div class="offer__container" style="grid-gap: 12px;">
          <div class="offer__item pa-3 pa-sm-4 pa-md-5 pa-lg-6" v-for="(method, m) in methods" :key="m" data-aos="zoom-in">
            <div class="title">{{ method.title }}</div>
            <p style="text-align: justify !important;">{{ method.desc }}</p>
          </div>
        </div>
      </v-container>
    </div>
    <div class="pt-10 pt-sm-12 pt-md-14 pt-lg-16">
      <div class="px-3 text-center mb-4">
        <div class="headline">We work on latest technologies</div>
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quod esse voluptates consequuntur pariatur fuga distinctio? <br> Ut, sapiente a dolores magnam ea voluptatum, possimus, est rerum ab illum reiciendis quibusdam amet?</p>
      </div>
      <div class="techs">
        <div class="tech__item pa-3 pa-sm-4 pa-md-5 pa-lg-6" v-for="(tech, t) in techs" :key="t" :style="{ backgroundColor: tech.color }" data-aos="zoom-in">
          <img :src="tech.img" :alt="tech.title">
          <p class="mt-2 font-weight-bold">{{ tech.title }}</p>
        </div>
      </div>
    </div>
  </div>  
</template>

<script>
export default {
  data: () => ({
    services: [
      { icon: 'mdi-webpack', name: 'web development', },
      { icon: 'mdi-cellphone', name: 'mobile app', },
      { icon: 'mdi-web', name: 'hosting', },
      { icon: 'mdi-gesture-double-tap', name: 'on demand app', },
      { icon: 'mdi-elevation-rise', name: 'digital marketing', },
      { icon: 'mdi-shopping-outline', name: 'e-commerce', },
    ],
    methods: [
      { title: 'Progressive Web Applications', desc: 'Progressive Web Applications is the following enormous thing in the realm of versatile Apps and web development solutions. It’s an application that can be gotten to without downloading a portable application. PWA gives applications like understanding to clients directly in their programs through its advanced web capacities. This is slanting and picking up its force due to its ability to work disconnected and match up substance to different gadgets.' },
      { title: 'Single Page Applications', desc: 'A solitary page application is a web application or site that interfaces with the client by progressively changing the current page as opposed to stacking whole new pages from a worker. This methodology will abstain from intruding on client collaboration between sequential pages. SPA saves guests from the troublesome route and twirling menus and adjusts to any gadget.' },  
      { title: 'WebAssembly', desc: 'WebAssembly is another huge accomplishment in the web improvement world. This is viewed as the closest companion of JavaScript with some announcing the up and coming age of Javascript which is a little and quick parallel configuration that guarantees close local execution for web applications. WebAssembly can assist designers with building rapid web applications that are especially required in games, music, CAD applications, video altering, and transferring.' },
      { title: 'Utilization of Chatbots', desc: 'In the event that you embrace a Chatbot, at that point, it will upgrade your online help by giving more accommodation to your clients. As per the NewVoiceMedia research report, organizations bear the loss of almost $62 million consistently in light of badly arranged client administrations in the USA. Chatbots are generally trusted to fulfill client care needs well indeed. Furthermore, you will likewise be profited by the day in and day out help. Doing as such, you can spare the compensation of a full-time online client assistance agent and spend that on something attainable.' },
      { title: 'Movement User Interface (UI) Design', desc: 'Clients today request remarkable client experience, a better UI plan that is simple than use with natural safe progression of data is the mystery of drawing in target crowds. Site pages created with appealing and intuitive components and intriguing page format will have clients running to website pages and convey expanded harp time on site pages. Innovative enlivened headers and pennants, vivified outlines, foundation liveliness, and drift impacts offer life to pages and draw in clients are some of the best technology to build website.' },
    ],
    techs: [
      { img: require('../assets/icons/html-5.png'), title: 'HTML5', color: 'rgb(252 73 11 / 10%)' },
      { img: require('../assets/icons/css-3.png'), title: 'CSS3', color: 'rgb(33 150 243 / 10%)' },
      { img: require('../assets/icons/sass.png'), title: 'SASS', color: 'rgb(206 107 156 / 10%)' },
      { img: require('../assets/icons/javascript.png'), title: 'JavaScript', color: 'rgb(247 224 24 / 10%)' },
      { img: require('../assets/icons/bootstrap.png'), title: 'Bootstrap', color: 'rgb(109 57 185 / 10%)' },
      { img: require('../assets/icons/bulma.png'), title: 'Bulma', color: 'rgb(0 209 178 / 10%)' },
      { img: require('../assets/icons/jquery.png'), title: 'JQuery', color: 'rgb(18 102 169 / 10%)' },
      { img: require('../assets/icons/vue.png'), title: 'Vue', color: 'rgb(66 184 131 / 10%)' },
      { img: require('../assets/icons/vuetify.png'), title: 'Vuetify', color: 'rgb(24 103 192 / 10%)' },
      { img: require('../assets/icons/react.png'), title: 'React JS', color: 'rgb(97 218 251 / 10%)' },
      { img: require('../assets/icons/firebase.png'), title: 'Firebase', color: 'rgb(245 127 23 / 10%)' },
      { img: require('../assets/icons/flutter.png'), title: 'Flutter', color: 'rgb(69 209 253 / 10%)' },
      { img: require('../assets/icons/photoshop.png'), title: 'Photoshop', color: 'rgb(49 197 240 / 10%)' },
      { img: require('../assets/icons/adobe-xd.png'), title: 'Adob XD', color: 'rgb(255 43 194 / 10%)' },
      { img: require('../assets/icons/react.png'), title: 'React Native', color: 'rgb(97 218 251 / 10%)' },
      { img: require('../assets/icons/node-js.png'), title: 'Node', color: 'rgb(131 205 41 / 10%)' },
      { img: require('../assets/icons/mongodb.png'), title: 'MongoDB', color: 'rgb(77 165 63 / 10%)' },
      { img: require('../assets/icons/mysql.png'), title: 'MySQL', color: 'rgb(195 124 11 / 10%)' },
      { img: require('../assets/icons/wordpress.png'), title: 'Wordpress', color: 'rgb(33 117 155 / 10%)' },
      { img: require('../assets/icons/php.png'), title: 'PHP', color: 'rgb(119 123 179 / 10%)' },
      { img: require('../assets/icons/framework7.png'), title: 'Framework7', color: 'rgb(238 53 15 / 10%)' },
      { img: require('../assets/icons/material-ui.png'), title: 'Material UI', color: 'rgb(0 129 203 / 10%)' },
    ] 
  })  
}
</script>

<style scoped>
/* Offers */
.offer__container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(31%, 1fr));
  grid-gap: 20px;
}
.offer__item {
  border-radius: 4px;
  box-shadow: 0 5px 15px 0 rgb(156 39 176 / 10%);
}

/* Technologies */
.techs {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(12%, 1fr));
  grid-gap: 1px;
}
.tech__item { 
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.tech__item img { height: 70px; }
p { 
  margin-bottom: 0 !important;
  text-align: center !important;
  margin-top: 2px;
}

@media (max-width: 1160px) {
  .techs { grid-template-columns: repeat(auto-fit, minmax(14%, 1fr)); }
}
@media (max-width: 1060px) {
  .techs { grid-template-columns: repeat(auto-fit, minmax(16%, 1fr)); }
}
@media (max-width: 920px) {
  .techs { grid-template-columns: repeat(auto-fit, minmax(18%, 1fr)); }
}
@media (max-width: 840px) {
  .offer__container { grid-template-columns: repeat(auto-fit, minmax(48%, 1fr)); }
}
@media (max-width: 780px) {
  .techs { grid-template-columns: repeat(auto-fit, minmax(20%, 1fr)); }
}
@media (max-width: 500px) {
  .offer__container { grid-template-columns: repeat(auto-fit, minmax(100%, 1fr)); }
  .techs { grid-template-columns: repeat(auto-fit, minmax(32%, 1fr)); }
}
@media (max-width: 360px) {
  .techs { grid-template-columns: repeat(auto-fit, minmax(49%, 1fr)); }
}
</style>