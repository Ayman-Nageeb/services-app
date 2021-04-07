<template>
  <div class="">
    <v-container style="background-color: white">
      <v-row>
        <v-col cols="12" sm="4">
          <div class="box">
            <service
              color="#ffff65"
              subtitle="We are all users."
              title="User Experience"
              image="https://www.codigo.co/img/views/services/services-postIt@2x.png"
              text="With over 200 digital projects and counting, we get what users want and need pretty easily. UX is the core to everything we build. In Codigo, we take user research, competitive analysis, wireframes, user flows, content maps very seriously."
            />
          </div>
        </v-col>
        <v-col cols="12" sm="4">
          <div class="box">
            <service
              color="#eed9dc"
              subtitle="We live to design."
              title="Interface Design"
              image="https://www.codigo.co/img/views/services/services-pixCherry@2x.png"
              text="We have pixel OCD. We keep ourselves constantly inspired with the hype and trends in the design industry to craft gorgeous interactions for your brand."
            />
          </div>
        </v-col>

        <v-col cols="12" sm="4">
          <div class="box">
            <service
              color="#b3262e"
              subtitle="We live to design."
              title="Interface Design"
              image="https://www.codigo.co/img/views/services/services-letterSeal@2x.png"
              text="We have pixel OCD. We keep ourselves constantly inspired with the hype and trends in the design industry to craft gorgeous interactions for your brand."
            />
          </div>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12" sm="4">
          <div class="box">
            <service
              color="#1988e8"
              subtitle="We live to design."
              title="Interface Design"
              image="https://www.codigo.co/img/views/services/services-phone@2x.png"
              text="We have pixel OCD. We keep ourselves constantly inspired with the hype and trends in the design industry to craft gorgeous interactions for your brand."
            />
          </div>
        </v-col>
        <v-col cols="12" sm="4">
          <div class="box">
            <service
              color="#18a152"
              subtitle="We live to design."
              title="Interface Design"
              image="https://www.codigo.co/img/views/services/services-cogwheels@2x.png"
              text="We have pixel OCD. We keep ourselves constantly inspired with the hype and trends in the design industry to craft gorgeous interactions for your brand."
            />
          </div>
        </v-col>
      </v-row>
    </v-container>
    <div class="my-16"></div>
  </div>
</template>

<script>
import service from "./service.vue";
export default {
  components: { service },
};
</script>

<style scoped>
.box {
  width: 400px;
  height: 400px;
}
</style>
