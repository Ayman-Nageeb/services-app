<template>
  <footer>
    <div class="footer">
      <h1 style="color: #d5333e; text-align: center !important" class="mb-12">
        Let’s have a chat
      </h1>
      <v-container class="">
        <v-row>
          <v-col cols="12" sm="3">
            <fitem name="build" @showcontactdrawer="$emit('showcontactdrawer')" />
          </v-col>
          <v-col cols="12" sm="3">
            <fitem name="build"  @showcontactdrawer="$emit('showcontactdrawer')" />
          </v-col>
          <v-col cols="12" sm="3">
            <fitem name="build" @showcontactdrawer="$emit('showcontactdrawer')" />
          </v-col>
          <v-col cols="12" sm="3">
            <fitem name="build" @showcontactdrawer="$emit('showcontactdrawer')" />
          </v-col>
        </v-row>
        <v-row>
          <v-col>
            <p class="text-center my-16">
              Copyright © Mohammed Elmostafa - Software Developer +9715 8890
              4955 • AbuHail, Dubai, UAE
            </p>
          </v-col>
        </v-row>
      </v-container>
    </div>
  </footer>
</template>

<script>
import fitem from "./item.vue";
export default {
  components: { fitem },
};
</script>

<style></style>
