<template>
  <div class="home">
    <!-- Home Banner with Text -->
    <div class="banner">
      <div class="banner__content">
        <div class="d-flex align-center">
          <span style="width: 100px; height: .5px; opacity: .5;" class="white" />
          &nbsp;&nbsp;&nbsp;<span style="font-size: large; opacity: .75;">The Best</span>&nbsp;&nbsp;&nbsp;
          <span style="width: 100px; height: .5px; opacity: .5;" class="white" />
        </div>
        <div class="mt-3 mt-sm-4 mt-md-5 mt-lg-6" style="font-size: x-large;">In Bussiness</div>
        <div class="text-center my-3 my-sm-4 my-md-5 my-lg-6" style="opacity: .65; font-size: 13px; letter-spacing: .5px;">Lorem ipsum dolor sit amet consectetur adipisicing elit. Impedit voluptatum aliquid</div>
        <div>
          <v-btn rounded width="200" large>
            <span>get started</span>
            <v-icon right size="16">mdi-arrow-right</v-icon>
          </v-btn>
        </div>
      </div>
      <div class="banner__img">
        <img src="https://wallpaperaccess.com/full/1393189.jpg" alt="Banner Image">
      </div>
    </div>

    <!-- About Us -->
    <div style="background-color: rgb(128 128 128 / 5%);">
      <v-container>
        <div class="home__about" data-aos="zoom-in">
          <div><img src="https://miro.medium.com/max/750/1*zJkojKNpFD9HFGPJLCs15Q.jpeg" alt="Spell Innovation"></div>
          <div class="pa-4 pa-sm-6 pa-md-8 pa-lg-10">
            <div class="text-h5 text-md-h4 mb-2" data-aos="fade-left">About Us</div>
            <p class="text-justify" data-aos="fade-right">{{ intro1 }}</p>
            <v-btn to="/about" data-aos="zoom-in" rounded width="150" dark style="background: linear-gradient(90deg, rgba(243,108,39,1) 0%, rgba(156,39,176,1) 100%);">
              <span class="text-capitalize">more</span>
              <v-icon size="16" right>mdi-arrow-right</v-icon>
            </v-btn>
          </div>
        </div>
      </v-container>
    </div>

    <!-- Services -->
    <div>
      <v-container class="py-10 py-sm-12 py-md-14 py-lg-16">
        <div data-aos="fade-up" class="d-flex justify-space-between align-center">
          <div class="display-1">Our Services</div>
          <v-btn color="primary" rounded width="110" to="/services">
            <span v-text="'More'" />
            <v-icon small right v-text="'mdi-arrow-right'" />
          </v-btn>
        </div>
        <div class="services__container mt-3">
          <div class="services__container__item px-3 py-6 px-sm-4 py-sm-8 px-md-5 py-md-10 px-lg-6 py-lg-12" v-for="(item, i) in  services" :key="i" data-aos="zoom-in">
            <v-icon class="pa-4" style="background: linear-gradient(90deg, rgba(243,108,39,1) 0%, rgba(156,39,176,1) 100%);  border-radius: 50%;" color="white">{{ item.icon }}</v-icon>
            <div class="mb-1 mt-4 text-capitalize" style="line-height: 1.2; font-weight: bold; display: block; font-size: 20px;">{{ item.name }}</div>
            <p class="text-center">There are many variations of passages of lorem Ipsum available but the new majority have suffered.</p>
          </div>
        </div>
      </v-container>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    intro1: 'We are living in the era of Information Technology. There is no need to describe the importance and significance of the wide - spread use of information technology. FourCoders Pvt. Ltd. is a young company in Kathmandu, Nepal. We FourCoders say we’re young because we’re peopled by young, energetic, curious and committed minds who are excited to solve one stop automated solution for your trade, industry, institution, organization and invention...',
    services: [
      { icon: 'mdi-webpack', name: 'web development', },
      { icon: 'mdi-cellphone', name: 'mobile app', },
      { icon: 'mdi-web', name: 'hosting', },
      { icon: 'mdi-gesture-double-tap', name: 'on demand app', },
      { icon: 'mdi-elevation-rise', name: 'digital marketing', },
      { icon: 'mdi-shopping-outline', name: 'e-commerce', },
    ],
  })
}
</script>

<style scoped>
/* Banner */
.banner {
  position: relative;
  color: white;
}
.banner__content {
  height: 100%;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  position: absolute;
  background-color: rgb(0 0 0 / 20%);
}
.v-btn {
  background: linear-gradient(90deg, rgba(243,108,39,1) 0%, rgba(156,39,176,1) 100%);
  color: white;
}

/* Home About */
.home__about {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(48%, 1fr));
  margin: 50px auto;
}

/* Services Container */
.services__container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(31%, 1fr));
  grid-gap: 20px;
}
.services__container__item {
  border: 1px solid rgba(0 0 0 / 10%);
  transition: ease-in-out 250ms;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  overflow: hidden;
}
.services__container__item:hover {
  transform: translateY(-6px);
  box-shadow: 0 10px 20px 0 rgba(0 0 0 / 20%);
  border: 1px solid transparent;
  border-radius: 4px;
}

@media (max-width: 1060px) {
  .home__about { margin: 40px auto; }
  .services__container { grid-gap: 16px; grid-template-columns: repeat(auto-fit, minmax(32%, 1fr)); }
}
@media (max-width: 840px) {
  .home__about { margin: 30px auto; }
  .services__container { grid-gap: 12px; grid-template-columns: repeat(auto-fit, minmax(48%, 1fr)); }
}
@media (max-width: 600px) {
  .home__about { grid-template-columns: repeat(auto-fit, minmax(100%, 1fr)); }
}
@media (max-width: 500px) {
  .home__about { margin: 20px auto; }
  .services__container { grid-gap: 12px; grid-template-columns: repeat(auto-fit, minmax(100%, 1fr)); }
}
</style>