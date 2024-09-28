<template>
  <v-container>
    <v-row>
      <v-col cols="12" class="card py-6 px-8">
        <v-col cols="12" class="pa-0">
          <div class="heading">Karma</div>
        </v-col>
        <v-col class="pa-0 mb-7">
          <div class="text my-2">
            Regularly evaluates our talent to ensure quality
            <span class="invisible-text">
              Monitors activity to identiy project
            </span>
          </div>
        </v-col>
        <v-col cols="12" class="d-flex justify-end">
          <img src="/src/assets/icon-karma.svg" alt="" />
        </v-col>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
</script>

<style scoped>
@font-face {
  font-family: f1;
  src: url(/src/assets/Poppins-SemiBold.ttf);
}
.heading {
  color: hsl(234, 12%, 34%);
  font-family: f1;
  font-size: 20px;
}
.text {
  color: hsl(229, 6%, 66%);
  font-size: 12px;
}
.card {
  background-color: #ffffff;
  border-radius: 10px;
  border-top: 5px solid hsl(34, 97%, 64%);
  box-shadow: 0px 14px 14px hsl(213, 39%, 89%); /* Adding drop shadow */
}
.invisible-text {
  visibility: hidden; /* This hides the text but keeps the space */
}
</style>