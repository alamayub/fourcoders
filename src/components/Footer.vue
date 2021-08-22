<template>
  <v-footer padless color="primary" class="py-4 py-sm-8 py-md-12 py-lg-16" dark>
    <div class="container">
      <div class="footer mb-6">
        <div class="text-center">
          <div class="footer__logo">
            <img src="../assets/fourcoders.png" alt="FourCoders Logo" >
          </div>
          <div class="mt-4 d-flex flex-wrap justify-center" style="grid-gap: 6px;">
            <v-btn icon v-for="(social, i) in socials" :key="i" target="_blank" :href="social.to">
              <v-icon size="18">{{ social.icon }}</v-icon>
            </v-btn>  
          </div>
        </div>
        <div>
          <div class="footer__content__title">
            <span>Company</span>
          </div>  
          <div class="d-inline-flex flex-column">
            <span v-for="(c, i) in company" :key="i">{{ c.title }}</span>  
          </div>
        </div>
        <div>
          <div class="footer__content__title">
            <span>Services</span>
          </div>  
          <div class="d-inline-flex flex-column">
            <span v-for="(c, i) in business" :key="i">{{ c.title }}</span>  
          </div>
        </div>
        <div>
          <div class="footer__content__title">
            <span style="lin-height: 1;">FourCoders&nbsp;Pvt. Ltd.</span>
          </div>  
          <div style="display: grid; grid-gap: 4px;">
            <div v-for="(c, i) in contacts" :key="i" class="d-flex" style="grid-gap: 8px;">
              <div><v-icon size="20">{{ c.icon }}</v-icon></div>
              <div>{{ c.title }}</div>
            </div>
          </div>
        </div>
      </div>  
      <div class="pt-4 text-center" style="border-top: 1px solid #fff;">
        <div style="font-weight: 300; letter-spacing: .5px; opacity: .75;">@FourCoders.com {{ new Date().getFullYear() }}. All Right Reserved</div>  
      </div>  
    </div>
  </v-footer>
</template>

<script>
export default {
  data: () => ({
    socials: [
      { icon: 'mdi-facebook', to: 'https://www.facebook.com' },
      { icon: 'mdi-twitter', to: 'https://www.facebook.com' },
      { icon: 'mdi-linkedin', to: 'https://www.facebook.com' },
      { icon: 'mdi-instagram', to: 'https://www.facebook.com' }
    ],
    company: [
      { title: 'About Us', to: '/about' },
      { title: 'Portfolio', to: '/portfolio' },
      { title: 'Careers', to: '/career' },
      { title: 'Our Team', to: '/team' },
      { title: 'Contact us', to: '/contact' },
    ],
    business: [
      { title: 'Web Development', to: '/service/web-development' },
      { title: 'Mobile App', to: '/service/mobile-app' },
      { title: 'Web Hosting', to: '/service/web-hosting' },
      { title: 'On Demand App', to: '/service/ondemand-app' },
      { title: 'Degital Marketing', to: '/service/digital-marketing' },
      { title: 'E-commerce', to: '/service/e-commerce' },
    ],
    contacts: [
      { icon: 'mdi-map-marker', title: 'Birgunj-10, Nepal' },
      { icon: 'mdi-email', title: 'info@fourcoders.com' },
      { icon: 'mdi-cellphone', title: '+977 9876543210' },
    ],
  })  
}
</script>

<style scoped>
.footer {
  display: grid;
  grid-gap: 12px;
  grid-template-columns: repeat(auto-fit, minmax(23%, 1fr)); 
}
.footer__logo img {
  max-height: 150px;  
}
.footer__content__title {
  font-weight: bold;
  font-size: 25px;
  line-height: 1;  
  margin-bottom: 15px;
}
.footer__content__title span { border-bottom: 1px solid rgb(255 255 255 / 50%); }
@media (max-width: 760px) {
  .footer { grid-template-columns: repeat(auto-fit, minmax(48%, 1fr)); }  
}
@media (max-width: 500px) {
  .footer { grid-gap: 20px; grid-template-columns: repeat(auto-fit, minmax(100%, 1fr)); }  
  .footer__content__title { margin-bottom: 5px; }
}
</style>