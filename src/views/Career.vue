<template>
  <div class="career">
    <div class="text__banner" data-aos="zoom-in">
      <div class="text__banner__content pa-3">
        <div style="line-height: 1;" class="display-1">Careers</div>
        <p class="my-4" style="opacity: .9; text-align: center !important;">Lorem ipsum dolor sit amet consectetur adipisicing elit. Impedit, obcaecati? <br> Id similique, quasi earum, amet magnam provident eum adipisci perferendis <br> necessitatibus natus soluta neque esse? Iure quasi quos suscipit dolores!</p>
        <v-btn data-aos="zoom-in" rounded width="150" color="primary">
          <span class="text-capitalize">join us</span>
        </v-btn>
      </div>
    </div>
    <v-container class="py-10 py-sm-12 py-md-14 py-lg-16">
      <div class="headline text-center font-weight-bold" data-aos="fade-up">Why Join Us</div>  
      <div class="join mt-4 mt-sm-6 mt-md-8 mt-lg-10">
        <div class="join__item pa-4 pa-sm-6 pa-md-8 pa-lg-10" v-for="(benfit, b) in benefits" :key="b" data-aos="zoom-in">
          <div class="d-flex align-center" style="grid-gap: 8px;">
            <div class="title mb-2" style="line-height: 1;">{{ benfit.title }}</div>
            <v-avatar color="success lighten-4" size="20">
              <v-icon size="14" color="success">mdi-check</v-icon>
            </v-avatar>
          </div>  
          <p>{{ benfit.desc }}</p>
        </div>  
      </div>
    </v-container>

    <!-- Vacancies -->
    <v-container id="#join">
      <div class="text-center mb-5">
        <div class="headline mb-1">Want to join FourCoders?</div> 
        <p style="text-align: center !important;">Checkout our current openings, fill the application form. <br> We will get back to you.</p> 
      </div>
      <div class="vacancy d-flex flex-column" style="grid-gap: 16px;">
        <div class="vacancy__item pa-3 pa-sm-4 pa-md-5 pa-lg-6" v-for="(vacancy, v) in vacancies" :key="v" data-aos="zoom-in">
          <div style="width: 100%;">
            <div class="d-flex justify-space-between align-center">
              <div class="title">{{ vacancy.title }}</div>
              <div style="font-size: 13px; opacity: .75; font-weight: 500; letter-spacing: .5px;" class="primary--text">{{ vacancy.type }}, {{ vacancy.count }}</div>
            </div> 
            <p v-if="vacancy.desc" class="text-start mt-1" style="opacity: .6;">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque quae voluptas molestiae, natus, neque, consectetur quisquam vero aliquid incidunt ducimus necessitatibus vitae officia adipisci sit dolore voluptates quod! Cupiditate, enim!
            </p>
          </div> 
          <div>
            <v-icon size="30" color="primary" v-text="'mdi-chevron-right'" />  
          </div>
        </div>
      </div> 
    </v-container>

    <div class="pt-10 pt-sm-12 pt-md-14 pt-lg-16">
      <div class="headline text-center mb-4 mb-sm-6 mb-md-8 mb-lg-10 font-weight-bold">Life At FourCoders</div>
      <div class="images">
        <div class="image" v-for="(img, i) in images" :key="i" data-aos="zoom-in">
          <img :src="img" alt="Image Description">
        </div>
      </div>  
    </div>

    <!-- Vacancy fill up form -->
    <v-dialog v-model="dialog" max-width="500">
      <v-card>
        <v-card-title class="text-h5">Fill Up Application Form </v-card-title>
        <v-card-text>
          <v-form  ref="form" lazy-validation v-model="valid" class="d-flex flex-column" style="grid-gap: 12px;">
            <v-text-field v-model="item.name" label="Full Name*" dense outlined hide-details prepend-inner-icon="mdi-account" :rules="[ v => !!v || '' ]" />
            <v-text-field v-model="item.phone" label="Phone Number*" dense outlined hide-details prepend-inner-icon="mdi-phone" :rules="[ v => !!v || '' ]" />
            <v-text-field v-model="item.email" label="Email*" dense outlined hide-details prepend-inner-icon="mdi-email" :rules="[ v => !!v || '' ]" />   
            <v-textarea v-model="item.message" label="Cover Letter..." dense outlined hide-details prepend-inner-icon="mdi-message" rows="4" /> 
            <v-file-input v-model="resume" show-size counter dense outlined label="Upload Resume*" :rules="[ v => !!v || '' ]" /> 
            <v-btn rounded color="primary" max-width="200" :disabled="!valid" @click="submit">submit</v-btn>           
          </v-form>  
        </v-card-text>
      </v-card>
    </v-dialog>

  </div>  
</template>

<script>
export default {
  data: () => ({
    vacancies: [
      { title: 'Front-end Developer', type: 'Full Time', count: 4, desc: true },
      { title: 'Back-end Developer', type: 'Full Time', count: 2, desc: true },
      { title: 'Content Writer', type: 'Full Time', count: 1, desc: false },
      { title: 'UX/UI Designer', type: 'Part Time', count: 1, desc: false },
      { title: 'Marketing Manager', type: 'Full Time', count: 2, desc: true },  
    ],
    dialog: true, 
    valid: true,
    item: {
      name: null,
      phone: null,
      email: null,
      message: null,
      position: null,  
    }, 
    resume: null,
    images: [
      'https://cdn.corporatefinanceinstitute.com/assets/home-office1.jpeg',
      'https://miro.medium.com/max/1187/1*IQdJfacKYjGRWGJgGYpMOA.jpeg',
      'https://images.pexels.com/photos/2528118/pexels-photo-2528118.jpeg',
      'https://images.squarespace-cdn.com/content/v1/5c51362e9d5abb96a228b53b/1549431692124-YUL6FYCHM0PK1FZ0TEH2/134744_2BrandonParkDr_092.jpg',
      'https://asset.mansionglobal.com/editorial/9-ideas-for-home-office-design/assets/mVDNuOv9Jl/homeoffice_lead-2560x1400.jpeg',
      'https://commercialobserver.com/wp-content/uploads/sites/3/2020/06/Hero-image-office.jpg',
      'https://www.avepoint.com/blog/wp-content/uploads/2018/10/iStock-887882750.jpg',
      'https://images.financialexpress.com/2021/01/1-704.jpg',
      'https://images.adsttc.com/media/images/6077/21f1/f91c/81f9/7400/03c7/newsletter/novita-office-nyc-31web.jpg',
      'https://stylesatlife.com/wp-content/uploads/2020/11/Elegant-Small-Office-Space-Design-Idea.jpg.webp',
      'https://www.betterteam.com/images/office-assistant-job-description-6100x4067-2020124.jpeg' 
    ],  
    benefits: [
      { title: 'Fast Growing Company', desc: 'We are at an inflection point to achieve accelaration' },
      { title: 'Greate Colleagues', desc: 'Closely tied and supportive team' } ,
      { title: 'Take Change', desc: 'As much as you are willing to take and show excellence' },
      { title: 'Don\'t Stop Learning', desc: 'An atmosphere where learning is always on top of to do list' },
      { title: 'Latest Technology Stack', desc: 'Working experience at cutting edge technologies' },
      { title: 'Cross Domain Exposure', desc: 'Highly passionate and cohassive team of technology and business people' }
    ],
    perks: [
      { title: 'Flexible Hours', icon: 'mdi-watch' },
      { title: '0% of Revenue', icon: 'mdi-finance' },
      { title: 'Pro Tools', icon: 'mdi-tools' },
      { title: 'Gaming', icon: 'mdi-google-controller' },
      { title: 'Remote Friendly', icon: 'mdi-remote-desktop' },
      { title: 'Cosy Studio', icon: 'mdi-sofa-outline' }, 
    ] 
  }),
  methods: {
    submit() {
      if(this.$refs.form.validate()) console.log('validate')
      else console.log('not validated')  
    }  
  } 
}
</script>

<style scoped>
/* .text__banner { background: none !important; } */

/* Join Us */
.join {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(30%, 1fr));
  grid-gap: 40px;  
}
p {
  text-align: start !important;
  margin-bottom: 0 !important;  
}
.join__item { 
    border-radius: 4px;
    box-shadow: 0 5px 15px 0 rgb(156 39 176 / 10%);
    /* background: linear-gradient(to top right, rgba(243 108 39 / 100%) 50%, rgba(156 39 176 / 100%) 50%); */
}
/* Images */
.images {
  display: grid; 
  grid-template-columns: repeat(auto-fit, minmax(20%, 1fr)); 
}
.images img { object-fit: cover !important; }

/* Vacancy */
.vacancy__item {
  box-shadow: 0 3px 10px 0 rgb(0 0 0 / 10%);
  border-radius: 4px;
  overflow: hidden;  
  display: flex;
  align-items: center;
  grid-gap: 12px;
  cursor: pointer;
}
@media (max-width: 1060px) {
  .join { grid-gap: 35px; }  
  .images { grid-template-columns: repeat(auto-fit, minmax(25%, 1fr)); }
}
@media (max-width: 860px) {
  .join { 
    grid-template-columns: repeat(auto-fit, minmax(46%, 1fr));  
    grid-gap: 30px; 
  }  
  .images { grid-template-columns: repeat(auto-fit, minmax(33%, 1fr)); }
}
@media (max-width: 760px) {
  .join { grid-gap: 25px; }  
}
@media (max-width: 500px) {
   .join { 
    grid-template-columns: repeat(auto-fit, minmax(100%, 1fr));  
    grid-gap: 16px; 
  }
  .images { grid-template-columns: repeat(auto-fit, minmax(50%, 1fr)); }
}
</style>