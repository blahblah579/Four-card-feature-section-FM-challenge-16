<template>
  <v-container fluid class="main">
    <v-row>
      <v-col cols="12" class="d-flex justify-center flex-column align-center">
        <div class="heading">Reliable, efficient delivery</div>
        <div class="tagline">Powered by Technology</div>
        <div class="para mb-10 mb-sm-7">
          Our Artificial Intelligence powered tools use millions of project data
          points to ensure that your project is successful
        </div>
      </v-col>
      <!-- SMALL -->
      <v-col
        class="small d-flex flex-column align-center"
        v-if="!isScreenLarge"
      >
        <div class="1">
          <CardPage1 />
        </div>
        <div class="23 d-flex flex-column">
          <div class="2"><CardPage2 /></div>
          <div class="3"><CardPage3 /></div>
        </div>
        <div class="4">
          <CardPage4 />
        </div>
      </v-col>

      <!-- LARGE -->
      <v-col
        class="big d-flex flex-column flex-md-row align-center mt-"
        v-if="isScreenLarge"
      >
        <v-col
          style="height: 100px"
          cols="12"
          sm="6"
          md="4"
          class="d-flex align-center"
        >
          <CardPage1 />
        </v-col>
        <v-col cols="12" sm="6" md="4">
          <div class="mb-7">
            <CardPage2 />
          </div>
          <div><CardPage3 /></div>
        </v-col>
        <v-col cols="12" sm="6" md="4" class="d-flex align-center">
          <CardPage4 />
        </v-col>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import CardPage1 from "./CardPage1.vue";
import CardPage2 from "./CardPage2.vue";
import CardPage3 from "./CardPage3.vue";
import CardPage4 from "./CardPage4.vue";

import { ref, computed, onMounted, onUnmounted } from "vue";

// Computed property to detect if the screen is large enough
const isScreenLarge = ref(window.innerWidth > 959.5);

// Function to update screen size dynamically
const updateScreenSize = () => {
  isScreenLarge.value = window.innerWidth > 959.5;
};

// Attach event listener to detect window resize
onMounted(() => {
  window.addEventListener("resize", updateScreenSize);
});

// Cleanup the event listener on component unmount
onUnmounted(() => {
  window.removeEventListener("resize", updateScreenSize);
});
</script>
<style scoped>
@font-face {
  font-family: f1;
  src: url(/src/assets/Poppins-ExtraLight.ttf);
}
@font-face {
  font-family: f2;
  src: url(/src/assets/Poppins-SemiBold.ttf);
}
.heading {
  font-family: f1;
  font-size: 30px;
  text-align: center;
  color: hsl(234, 12%, 34%);
}
.tagline {
  font-family: f2;
  font-size: 30px;
  text-align: center;
  color: hsl(234, 12%, 34%);
}
.para {
  color: hsl(229, 6%, 66%);
  padding-left: 300px;
  padding-right: 300px;
  text-align: center;
}
.main {
  padding-left: 76px;
  padding-right: 76px;
}

/* Media query for screen size 959.5px or smaller */
@media (max-width: 959.5px) {
  .para {
    padding-left: 100px;
    padding-right: 100px;
  }
}

/* Media query for screen size 599.5px or smaller */
@media (max-width: 599.5px) {
  .para {
    padding-left: 20px;
    padding-right: 20px;
  }
}
</style>