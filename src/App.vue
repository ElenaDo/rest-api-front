<template>
  <v-app>
    <h1 class="text-center">Rest API</h1>
    <v-form>
    <v-container>
      <v-row>
        <v-col
          cols="12"
          md="3"
        >
          <v-text-field
            :counter="10"
            label="First name"
            required
          ></v-text-field>
        </v-col>

        <v-col
          cols="12"
          md="3"
        >
          <v-text-field
            :counter="10"
            label="Last name"
            required
          ></v-text-field>
        </v-col>

        <v-col
          cols="12"
          md="3"
        >
          <v-text-field
            label="E-mail"
            required
          ></v-text-field>
        </v-col>
        <v-col
          cols="12"
          md="3"
        >
        <v-btn color="primary">Create</v-btn>
        </v-col>
      </v-row>
      <v-card>
        <v-card-title>Name</v-card-title>
      </v-card>
    </v-container>
  </v-form>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  components: {
  },

  data: () => ({
    //
  }),
};
</script>
