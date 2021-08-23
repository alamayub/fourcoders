<template>
  <div class="py-10 py-sm-12 py-md-14 py-lg-16">
    <v-container>
      <div class="text-center mb-6">
        <div class="display-1">Meet Our Team</div>  
        <div style="font-size: 15px; letter-spacing: 1px; font-weight: 300;">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Dolor earum porro minus repellat, unde quibusdam cupiditate, fugiat, facilis aliquid accusamus sequi quidem sapiente est rem nihil repellendus temporibus doloremque maiores.</div>  
      </div>
      <div class="team">
        <div class="team__item d-flex pa-4 pa-sm-5 pa-md-6 pa-lg-7" style="grid-gap: 20px;" v-for="a in 7" :key="a" data-aos="zoom-in">
          <div class="team__img">
            <img src="https://static-koimoi.akamaized.net/wp-content/new-galleries/2020/10/peaky-blinders-do-you-know-cillian-murphy-as-thomas-shelby-smoked-3000-cigarettes-in-just-2-seasons-002.jpg" alt="Thomas Shelby">  
          </div>
          <div>
            <div class="title" style="line-height: 1;">Thomas Shelby</div>
            <div style="font-size: 15px; letter-spacing: 1px; font-weight: 300;" class="mt-1 mb-2 primary--text">
              <span style="border-bottom: 1px solid;">Peaky Blinders (CEO)</span>  
            </div>  
            <p class="mb-0">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Eius, soluta quas accusantium temporibus blanditiis necessitatibus omnis porro laudantium perspiciatis sequi. Et mollitia fuga vitae dolorem sapiente accusantium explicabo pariatur sunt.</p>
          </div>
          <div>
            <v-btn icon v-for="(social, s) in socials" :style="{ color: social.color }" :key="s" target="_blank" :href="social.to">
              <v-icon v-text="social.icon" :style="{ color: social.color }" size="20" />
            </v-btn>  
          </div>
        </div>
      </div>  
    </v-container>
  </div>  
</template>

<script>
export default {
  data: () => ({
    socials: [
      { icon: 'mdi-facebook', to: 'https://www.facebook.com', color: '#3b5998' },
      { icon: 'mdi-twitter', to: 'https://www.twitter.com', color: '#00acee'  },
      { icon: 'mdi-linkedin', to: 'https://www.linkedin.com', color: '#0e76a8' },
      { icon: 'mdi-instagram', to: 'https://www.instagram.com', color: '#8a3ab9' }
    ]  
  })  
}
</script>

<style scoped>
.team {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(48%, 1fr));
  grid-gap: 20px;  
}
.team__item {
  border: 1px solid rgba(0 0 0 / 10%);
  transition: ease-in-out 250ms;
}
.team__item:hover {
  transform: translateY(-6px);
  box-shadow: 0 10px 20px 0 rgba(0 0 0 / 20%);
  border: 1px solid transparent;
  border-radius: 4px;
}
.team__img img {
  height: 125px !important;
  width: 125px !important;
  border-radius: 50%; 
  overflow: hidden; 
  object-fit: cover !important; 
}
p { font-size: 14px !important; }
@media (max-width: 760px) {
  .team { 
    grid-template-columns: repeat(auto-fit, minmax(100%, 1fr));
    grid-gap: 16px;
  }  
}
@media (max-width: 500px) {
  .team__item { 
    flex-direction: column;
    align-items: center;
    text-align: center;  
  }  
  p { text-align: center !important; }
}
</style>