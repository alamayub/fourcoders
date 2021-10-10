<template>
  <v-footer color="white" class="py-6 py-sm-8 py-md-10 py-lg-12 elevation-6" padless>
    <v-container class="footer">
      <div class="company">
        <img src="../assets/logo.png" alt="FourCoders - Your Dream Achiever" style="height: 100px;">   
        <div class="mt-3 mb-4 para">FourCoders - Your Dream Achiever</div>
        <div class="socials mt-4">
          <span class="para font-weight-bold black--text">Follow Us : </span>  
          <v-btn icon small v-for="(social, s) in socials" :key="s" :color="social.color" target="_blank" :href="social.to">
            <v-icon size="14">{{ social.icon }}</v-icon>
          </v-btn>  
        </div>
      </div>
      <div class="footer__links">
        <div class="links">
          <div class="link__title">Company</div>
          <div class="para" v-for="(inf, i) in info" :key="i">{{ inf }}</div>
        </div>
        <div class="links">
          <div class="link__title">Links</div>
          <div class="para" v-for="(link, l) in links" :key="l">{{ link }}</div>
        </div>
        <div class="links">
          <div class="link__title">Services</div>
          <div class="para" v-for="(service, s) in services" :key="s">{{ service }}</div>
        </div>
        <div class="links">
          <div class="link__title">Contact</div>
          <div class="para" v-for="(con, c) in contact" :key="c">{{ con }}</div>
        </div>  
      </div>
    </v-container>  
    <v-container class="pt-6">
      <v-divider />
      <div class="text-center mt-6"><span class="para">Copyright @{{ new Date().getFullYear() }}</span> <span class="link__title">FourCoders</span></div>
    </v-container>
  </v-footer>
</template>

<script>
export default {
  data: () => ({
    info: ['Home', 'About', 'Career'],
    links: ['Student', 'Business', 'Instructor'],
    services: ['Web Development', 'Mobile App', 'Web Hosting', 'On Demand App', 'Digitl Marketing', 'E-commerce'],
    contact: ['FourCoders Pvt. Ltd.', 'Birgunj-10, Napal', 'fourcoders2017@gmail.com', '+977 9814245916 | +977 9809167106'],
    socials: [
      { icon: 'mdi-facebook', to: 'https://www.facebook.com', color: '#3b5998' },
      { icon: 'mdi-twitter', to: 'https://www.twitter.com', color: '#00acee'  },
      { icon: 'mdi-linkedin', to: 'https://www.linkedin.com', color: '#0e76a8' },
      { icon: 'mdi-instagram', to: 'https://www.instagram.com', color: '#8a3ab9' }
    ],
  })  
}
</script>

<style scoped>
.footer {
  display: grid;
  grid-template-columns: 280px calc(100% - 330px);
  grid-gap: 50px;  
}
.send__btn {
  border-radius: 6px !important;
  position: absolute;
  right: 6px; 
  top: 6px; 
}
input {
  outline: none;
  border: none;
  background-color: rgba(128, 128, 128, 0.11);
  border-radius: 6px;
  padding: 12px;
  font-size: 12px;
  width: 100%;
  letter-spacing: .5px;
}
.footer__links {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(25%, 1fr));  
}
.para {
  color: #00063ab7;
  font-size: 13px; 
  font-weight: 400 !important;
}
.links .para { margin-bottom: 8px; }
.links .para:last-child { margin-bottom: 0 !important; }
.link__title {
  font-weight: bold;
  margin-bottom: 16px;  
  letter-spacing: .5px;
  font-size: 17px;
}
@media (max-width: 960px) {
  .footer { grid-gap: 40px; }  
  .footer__links { grid-template-columns: repeat(auto-fit, minmax(50%, 1fr)); }  
}
@media (max-width: 600px) {
  .footer { grid-template-columns: repeat(auto-fit, minmax(100%, 1fr)); grid-gap: 30px;  }  
  .footer__links { row-gap: 20px; }
}
</style>