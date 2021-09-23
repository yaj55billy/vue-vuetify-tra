<template>
  <div>
    <hello-world />
    <v-card flat class="py-12">
      <v-card-text>
        <v-row align="center" justify="center">
          <v-col cols="12">
            <p class="text-center">
              Mandatory
            </p>
          </v-col>
          <v-btn-toggle v-model="toggle_exclusive" mandatory>
            <v-btn>
              <v-icon>mdi-format-align-left</v-icon>
            </v-btn>
            <v-btn>
              <v-icon>mdi-format-align-center</v-icon>
            </v-btn>
            <v-btn>
              <v-icon>mdi-format-align-right</v-icon>
            </v-btn>
            <v-btn>
              <v-icon>mdi-format-align-justify</v-icon>
            </v-btn>
          </v-btn-toggle>
        </v-row>
      </v-card-text>
    </v-card>
    <v-carousel v-model="model">
      <v-carousel-item v-for="(color, i) in colors" :key="color">
        <v-sheet :color="color" height="100%" tile>
          <v-row class="fill-height" align="center" justify="center">
            <div class="text-h2">Slide {{ i + 1 }}</div>
          </v-row>
        </v-sheet>
      </v-carousel-item>
    </v-carousel>
  </div>
</template>

<script>
import HelloWorld from "../components/HelloWorld";

export default {
  name: "Home",
  components: {
    HelloWorld,
  },
  data() {
    return {
      toggle_exclusive: undefined,
      model: 0,
      colors: ["primary", "secondary", "yellow darken-2", "red", "orange"],
    };
  },
};
</script>
