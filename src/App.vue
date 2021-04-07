<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" temporary right app width="500px">
      <div class="pa-4">
        <v-card-title>
          <v-spacer></v-spacer>
          <v-btn
            large
            icon
            style="background-color: #493346"
            @click="hidecontactdrawer"
          >
            <v-icon color="white">mdi-close</v-icon>
          </v-btn>
        </v-card-title>
        <p class="display-1 font-weight-bold">Let’s chat about</p>
        <v-select
          outlined
          :items="[
            'Helping to build somthing',
            'test option',
            'Customising a Solution',
          ]"
          filled
          label="select item"
          v-model="data"
        ></v-select>
        <div>
          <p style="color: #d5333e">* Mandatory fields</p>
        </div>
      </div>
      <v-divider class=""></v-divider>
      <div class="my-4"></div>
      <p class="headline mx-3 font-weight-bold">Type of specialisation *</p>
      <div class="ma-4">
        <v-radio-group v-model="row" row>
          <v-radio label="UX Design" value="radio-1"></v-radio>
          <v-radio label="UI Design" value="radio-2"></v-radio>
          <v-radio label="Others" value="radio-3"></v-radio>
        </v-radio-group>
      </div>

      <p class="headline mx-3 font-weight-bold">No. of attendees *</p>
      <div class="px-4">
        <v-text-field
          type="text"
          placeholder="Expected class size"
          label="Size"
          outlined
          color
        ></v-text-field>
      </div>
      <div class="my-2"></div>
      <v-card-actions class="px-4 mb-4">
        <v-spacer></v-spacer>
        <v-btn large rounded color="#d5333e" dark>
          <span class="ma-4">Submit</span>
        </v-btn>
      </v-card-actions>
    </v-navigation-drawer>

    <v-container>
      <v-row>
        <v-col>
          <v-app-bar class="elevation-0 pt-4" color="white">
            <div class="d-flex align-center">
              <v-img
                alt="Vuetify Logo"
                class="shrink mr-2"
                contain
                src="https://www.codigo.co/img/ui/logo-codigo-red.svg"
                transition="scale-transition"
                width="150"
              />
            </div>

            <v-spacer></v-spacer>

            <span class="appbar-item mx-2">Work</span>
            <span class="appbar-item mx-2">Solution</span>
            <span class="appbar-item mx-2 font-weight-bold">Services</span>
            <span class="appbar-item mx-2">About us</span>
            <span class="appbar-item mx-2">Blog</span>

            <v-btn rounded color="#3a2837" dark large class="mx-2"
              ><span class="pa-4 text-">Request a quote</span></v-btn
            >
          </v-app-bar>
        </v-col>
      </v-row>

      <v-main>
        <div class="my-4">
          <ititle />
          <ttext />
          <services />
          <div class="my-16"></div>
          <appfooter @showcontactdrawer="showcontactdrawer" />
        </div>
      </v-main>
    </v-container>
  </v-app>
</template>

<script>
import ttext from "./components/intro/text.vue";
// import HelloWorld from "./components/HelloWorld";

import ititle from "./components/intro/title.vue";
import Services from "./components/services/Services.vue";
import appfooter from "./components/footer/Footer.vue";

export default {
  name: "App",

  components: { ititle, ttext, Services, appfooter },

  data: () => ({
    fadeInElements: [],
    drawer: false,
    data: "",
  }),
  onMounted() {
    this.fadeInElements = Array.from(
      document.getElementsByClassName("fade-in")
    );
    document.addEventListener("scroll", this.handleScroll);
    this.handleScroll();
  },
  methods: {
    handleScroll() {
      for (var i = 0; i < this.fadeInElements.length; i++) {
        var elem = this.fadeInElements[i];
        if (this.isElemVisible(elem)) {
          elem.style.opacity = "1";
          elem.style.transform = "scale(1)";
          this.fadeInElements.splice(i, 1); // only allow it to run once
        }
      }
    },
    isElemVisible(el) {
      var rect = el.getBoundingClientRect();
      var elemTop = rect.top + 200; // 200 = buffer
      var elemBottom = rect.bottom;
      return elemTop < window.innerHeight && elemBottom >= 0;
    },
    showcontactdrawer() {
      this.drawer = true;
    },
    hidecontactdrawer() {
      this.drawer = false;
    },
  },
};
</script>

<style scoped>
.appbar-item {
  margin-left: 5px;
  cursor: pointer;
  transition: 0.8s;
}

.appbar-item:hover {
  text-decoration: underline;
}

.fade-in {
  opacity: 0;
  transition: 0.3s all ease-out;
  transform: scale(0.8);
  box-sizing: border-box;
  padding: 20px;
  display: inline-block;
}
</style>
