<template>
  <v-app>
    <v-card>
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
          <v-list-item two-line>
            <v-list-item-content>
              <div class="overline mb-4">Lastname</div>
              <v-list-item-title class="headline mb-1">e-mail</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-card-actions>
        <v-btn text>Cancel</v-btn>
        <v-btn text>Delete</v-btn>
      </v-card-actions>
        </v-card>
      </v-container>
    </v-form>
    </v-card>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  components: {
  },

  data: () => ({
    form: {
      name: '',
      lastname: '',
      email: '',
    }
  }),
};
</script>
