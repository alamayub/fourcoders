<template>
  <div class="contact">
    <div class="contact__container">
      <div class="text-center primary--text" style="letter-spacing: .5px;">
        <div class="display-1 mb-2">Get in Touch</div>
        <div style="opacity: .5;">We want to hear from you. Let's know how we can help.</div>
      </div>
      <v-form v-model="valid" class="form mt-8 primary--text" lazy-validation ref="form">
        <div class="form__div">
          <div>
            <div class="mb-1">Full Name &nbsp;<span class="secondary--text">*</span></div>
            <v-text-field v-model="item.name" outlined rounded dense hide-details placeholder="ex. John Doe" :rules="[ v => !!v || '' ]" />
          </div>
          <div>
            <div class="mb-1">Phone Number &nbsp;<span class="secondary--text">*</span></div>
            <v-text-field v-model="item.phone" :counter="10" type="number" outlined rounded dense hide-details placeholder="ex. 9876543210" :rules="[ v => !!v || '', v => v.length == 10 || '' ]" />
          </div>
        </div>
        <div class="form__div">
          <div>
            <div class="mb-1">Email Address &nbsp;<span class="secondary--text">*</span></div>
            <v-text-field v-model="item.email" outlined rounded dense hide-details placeholder="ex. john@doe.com" :rules="[ v => !!v || '' ]" />
          </div>
          <div>
            <div class="mb-1">Select a Subject &nbsp;<span class="secondary--text">*</span></div>
            <v-select v-model="item.type" outlined rounded dense hide-details placeholder="Please Select*" :rules="[ v => !!v || '' ]" />
          </div>
        </div>
        <div>
          <div class="mb-1">Message</div>
          <v-textarea v-model="item.message" outlined rounded dense hide-details placeholder="Describe your task for us." />
        </div>
        <div>
          By submitting this form, you are agreeing to our Terms Condition and Privacy policy rules.
        </div>
        <div>
          <v-btn color="secondary" rounded width="120">submit</v-btn>
        </div>
      </v-form>
    </div>
    <!-- <div class="map">
      <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3554.482279355477!2d84.87663421500014!3d27.01492238308371!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x39935440af3b59e3%3A0x5aa0411733213e6a!2sBirgunj%20Ghanta%20Ghar!5e0!3m2!1sen!2snp!4v1629135428021!5m2!1sen!2snp" style="border:0;" allowfullscreen="" loading="lazy" />
    </div> -->
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
      type: null,
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
  max-width: 860px;
  margin-right: auto;
  margin-left: auto;
  padding: 12px;
}
.form {
  width: 100%;
  display: flex;
  flex-direction: column;
  grid-gap: 20px;
}
.form__div {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(45%, 1fr));
  grid-gap: 30px;
}
.map {
  height: 50vh;
  overflow: hidden;
}
iframe { 
  height: 100%;
  width: 100%;
}

@media (max-width: 500px) {
  .form { grid-gap: 16px; }
  .form__div {
    grid-template-columns: repeat(auto-fit, minmax(100%, 1fr));
    grid-gap: 16px;
  }
}
</style>