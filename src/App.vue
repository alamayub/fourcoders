<template>
  <v-app>
    <Navbar />
    <Sidebar />
    <v-main>
      <router-view :key="$route.path" />
    </v-main>
    <Footer />
  </v-app>
</template>

<script>
import Navbar from './components/Navbar'
import Sidebar from './components/Sidebar'
import Footer from './components/Footer'
export default {
  name: 'App',
  components: { Sidebar, Navbar, Footer },
  data: () => ({
    //
  }),
};
</script>


<style>
* { text-decoration: none; }
html { scroll-behavior: smooth; }
/* Container */
.container {
  max-width: 1250px;
  margin-right: auto;
  margin-left: auto;
  padding: 12px;
}
/* Image */
img {
  display: block;
  height: 100%;
  width: 100%;
  object-fit: contain;
}
/* Button */
.v-btn {
  font-weight: 300 !important;
  text-transform: capitalize !important;
  font-size: 13px !important;
  text-transform: capitalize !important;
}

p {
  font-size: 13px;
  letter-spacing: .5px;
  text-align: justify;
  font-weight: 300;
}

/* Text Fields */
/* .v-text-field--filled.v-input--dense.v-text-field--single-line > .v-input__control > .v-input__slot, 
.v-text-field--filled.v-input--dense.v-text-field--outlined > .v-input__control > .v-input__slot, 
.v-text-field--filled.v-input--dense.v-text-field--outlined.v-text-field--filled > .v-input__control > .v-input__slot, 
.v-text-field--full-width.v-input--dense.v-text-field--single-line > .v-input__control > .v-input__slot, 
.v-text-field--full-width.v-input--dense.v-text-field--outlined > .v-input__control > .v-input__slot, 
.v-text-field--full-width.v-input--dense.v-text-field--outlined.v-text-field--filled > .v-input__control > .v-input__slot, 
.v-text-field--outlined.v-input--dense.v-text-field--single-line > .v-input__control > .v-input__slot, 
.v-text-field--outlined.v-input--dense.v-text-field--outlined > .v-input__control > .v-input__slot, 
.v-text-field--outlined.v-input--dense.v-text-field--outlined.v-text-field--filled > .v-input__control > .v-input__slot {
  border-radius: 0 !important;
} */
.v-input input, .v-input textarea { 
  font-size: 13px !important; 
  letter-spacing: .75px !important; 
  /* color: #9c27b0 !important;  */
}
.v-input .v-label { 
  font-size: 13px !important; 
  letter-spacing: 1px !important; 
  /* color: rgb(156 39 176 / 40%) !important; */
}
.v-input__icon .v-icon.v-icon, .v-select-list .v-icon.v-icon { font-size: 16px !important; }
.v-text-field--outlined.v-input--is-focused fieldset { border: 1px solid #9c27b0 !important; }
.v-text-field--outlined.v-input--has-state fieldset { border: 1px solid #f36c27 !important; }

/* Number type spin wheels */
input[type=number]::-webkit-inner-spin-button, 
input[type=number]::-webkit-outer-spin-button { 
  -webkit-appearance: none; 
  margin: 0; 
}

/* Test banner */
.text__banner {
  background: linear-gradient(90deg, rgba(243,108,39,1) 0%, rgba(156,39,176,1) 100%);
  height: 60vh;
}
.text__banner__content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
  color: #fff;
  text-align: center;
  overflow: hidden;
}
.text__banner__content span {
  text-transform: uppercase;
  letter-spacing: 1px;
  line-height: 1 !important;
}
@media (max-width: 1060px) {
  .text__banner { height: 50vh; }
}
@media (max-width: 840px) {
  .text__banner { height: 40vh; }
}
</style>