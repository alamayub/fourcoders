<template>
  <div class="contact">
    <v-container class="contact__container">
      <div class="contact__info">

      </div>
      <v-form lazy-validation v-model="valid" ref="form" class="contact__form pa-4 pa-sm-6 pa-md-8 pa-lg-10">
        <div class="mb-2" style="line-height: 1;">
          <div style="font-size: 20px; margin-bottom: 3px;">Send Us Message</div> 
          <small>We'll get to you as soon as possible.</small> 
        </div>  
        <v-text-field v-model="item.name" label="Full Name*" outlined dense hide-details :rules="[ v => !!v || '' ]" prepend-inner-icon="mdi-account" />
        <v-text-field v-model="item.phone" label="Phone Number*" type="number" outlined dense hide-details :rules="[ v => !!v || '' ]" prepend-inner-icon="mdi-cellphone" />
        <v-text-field v-model="item.email" label="Email*" outlined dense hide-details :rules="[ v => !!v || '' ]" prepend-inner-icon="mdi-email" />
        <v-textarea v-model="item.message" label="Message" outlined dense hide-details prepend-inner-icon="mdi-message" />
        <v-btn rounded max-width="200" color="primary" @click.stop="sendMessage" :disabled="!valid">send message</v-btn>
      </v-form>  
    </v-container>
    <div class="map">
      <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3554.482279355477!2d84.87663421500014!3d27.01492238308371!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x39935440af3b59e3%3A0x5aa0411733213e6a!2sBirgunj%20Ghanta%20Ghar!5e0!3m2!1sen!2snp!4v1629135428021!5m2!1sen!2snp" style="border:0;" allowfullscreen="" loading="lazy" />
    </div>
  </div>  
</template>

<script>
export default {
  data: () => ({
    valid: true,
    item: {
      name: null,
      phone: null,
      email: null,
      message: null  
    }  
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
.contact__container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(48%, 1fr));
  grid-gap: 20px;
}
.contact__form {
  display: flex;
  flex-direction: column;
  grid-gap: 12px; 
  box-shadow: 0px 2px 4px -1px rgb(0 0 0 / 20%), 0px 4px 5px 0px rgb(0 0 0 / 14%), 0px 1px 10px 0px rgb(0 0 0 / 12%);
  border-radius: 4px; 
}
.map {
  height: 50vh;
  overflow: hidden;
}
iframe { 
  height: 100%;
  width: 100%;
}
</style>