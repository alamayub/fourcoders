<template>
  <div class="contact">
    <div class="text__banner" data-aos="zoom-in">
      <div class="text__banner__content text-h4 text-md-h3 text-lg-h2">
        <div style="line-height: 1;">FourCoders</div>
        <span class="mt-3 mt-md-5 text-h6 text-md-h5">Contact Us</span>
      </div>
    </div>
    <div style="background-color: rgb(128 128 128 / 4%);" class="py-10 py-sm-12 py-md-14 py-lg-16">
      <v-container>
        <p style="text-align: start !important; font-size: 14px !important;">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ipsam minima voluptate quos, fuga atque accusantium natus neque nisi quasi excepturi, alias ad saepe nulla consequuntur quibusdam assumenda pariatur maiores aut. Lorem ipsum dolor, sit amet consectetur adipisicing elit. Hic commodi iste nostrum, fugiat repudiandae quod reiciendis iusto quam repellat aut? Perferendis quam accusamus laudantium, dolorum natus officiis perspiciatis sit id?</p>
      </v-container>
    </div>
    <div class="py-10 py-sm-12 py-md-14 py-lg-16">
      <v-container class="form">
        <div class="contact__info" data-aos="fade-up">
          <div class="display-1 mb-3" style="line-height: 1;">Contact Info</div>
          <div style="font-size: 15px; letter-spacing: 1px; font-weight: 300;">Feel free to contact us anytime. We'll do our best to serve you.</div>
          <div class="d-flex flex-column my-6" style="grid-gap: 25px;">
            <div class="contact__item d-flex align-center" style="grid-gap: 16px;" v-for="(contact, c) in contacts" :key="c">
              <div class="primary pa-4" style="border-radius: 6px;">
                <v-icon v-text="contact.icon" color="white" />
              </div>
              <div>
                <div class="title" style="line-height: 1;">{{ contact.title }}</div>
                <div style="margin-top: 10px; font-size: 15px; letter-spacing: 1px; line-height: 1; font-weight: 300;">{{ contact.value }}</div>
              </div>
            </div>
          </div>
          <div class="socials">
            <v-btn icon v-for="(social, s) in socials" :style="{ color: social.color }" large :key="s" target="_blank" :href="social.to">
              <v-icon v-text="social.icon" :style="{ color: social.color }" size="24" />
            </v-btn>
          </div>
        </div>
        <div data-aos="fade-up">
          <div class="mb-4">
            <div class="display-1 mb-3" style="line-height: 1;">Leave Us Message</div>
            <div style="font-size: 15px; letter-spacing: 1px; font-weight: 300;">Lorem ipsum dolor sit amet consectetur adipisicing elit. Sapiente animi deleniti esse doloribus sunt consequuntur nam nobis, fuga ducimus?</div>
          </div>
          <v-form v-model="valid" class="primary--text d-flex flex-column" style="grid-gap: 20px;" lazy-validation ref="form">
            <div class="form__div">
              <v-text-field v-model="item.name" outlined dense hide-details label="Full Name*" :rules="[ v => !!v || '' ]" />
              <v-text-field v-model="item.phone" :counter="10" type="number" outlined dense hide-details label="Phone Number*" :rules="phoneRules" />
            </div>
            <div class="form__div">
              <v-text-field v-model="item.email" outlined dense hide-details label="Email*" :rules="emailRules" />
              <v-select v-model="item.type" :items="types" outlined dense hide-details label="Please Select*" :rules="[ v => !!v || '' ]" />
            </div>
            <v-textarea v-model="item.message" outlined dense hide-details label="Describe your task for us." />
            <div style="font-size: 14px; letter-spacing: .5px;" class="primary--text">By submitting this form, you are agreeing to our Terms Condition and Privacy policy rules.</div>
            <div class="text-end">
              <v-btn color="secondary" rounded width="150" large :disabled="!valid" @click.stop="sendMessage">submit</v-btn>
            </div>
          </v-form>
        </div>
      </v-container>
    </div>
    <div class="map" data-aos="zoom-in">
      <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3554.482279355477!2d84.87663421500014!3d27.01492238308371!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x39935440af3b59e3%3A0x5aa0411733213e6a!2sBirgunj%20Ghanta%20Ghar!5e0!3m2!1sen!2snp!4v1629135428021!5m2!1sen!2snp" style="border:0;" allowfullscreen="" loading="lazy" />
    </div>
  </div>  
</template>

<script>
export default {
  data: () => ({
    contacts: [
      { icon: 'mdi-map-marker', title: 'Address', value: 'Birgunj-10, Nepal' },
      { icon: 'mdi-phone', title: 'Phone', value: '+977 9814245916 | +977 9809167106' },
      { icon: 'mdi-email', title: 'Email', value: 'info@fourcoders.com' }
    ],
    socials: [
      { icon: 'mdi-facebook', to: 'https://www.facebook.com', color: '#3b5998' },
      { icon: 'mdi-twitter', to: 'https://www.twitter.com', color: '#00acee'  },
      { icon: 'mdi-linkedin', to: 'https://www.linkedin.com', color: '#0e76a8' },
      { icon: 'mdi-instagram', to: 'https://www.instagram.com', color: '#8a3ab9' }
    ],
    valid: true,
    item: {
      name: null,
      phone: '',
      email: null,
      type: null,
      message: null  
    },
    types: ['Web Development', 'Mobile App', 'Web Hosting', 'On Demand App', 'Digital Marketing', 'E-commerce'],
    phoneRules: [
      v => !!v || '',
      v => v.length === 10 || ''
    ],
    emailRules: [
      v => !!v || 'E-mail is required',
      v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
    ]
  }),
  methods: {
    sendMessage() {
      if(this.$refs.form.validate()) console.log('submitted')
      else console.log('nope')  
    }  
  } 
}
</script>

<style scoped>
.form {
  display: grid;
  grid-template-columns: calc(40% - 12px) calc(60% - 18px);
  grid-gap: 30px;
}
.form__div {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(45%, 1fr));
  grid-gap: 20px;
}
.field__title {
  font-size: 14px;
  letter-spacing: .5px;
  margin-bottom: 5px;
  opacity: .8;
}
.map {
  height: 50vh;
  overflow: hidden;
}
iframe { 
  height: 100%;
  width: 100%;
}

@media (max-width: 670px) {
  .form { grid-template-columns: repeat(auto-fit, minmax(100%, 1fr)); }
}

@media (max-width: 500px) {
  .form__div {
    grid-template-columns: repeat(auto-fit, minmax(100%, 1fr));
    grid-gap: 16px;
  }
}
</style>