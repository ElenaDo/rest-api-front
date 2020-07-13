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
              v-model="form.name"
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
              v-model="form.lastname"
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
              v-model="form.email"
              required
            ></v-text-field>
          </v-col>
          <v-col
            cols="12"
            md="3"
          >
          <v-btn color="primary" @click="createContact" :disabled="!canCreate">Create</v-btn>
          </v-col>
        </v-row>
        <div v-if="this.contacts.length">
          <v-card class="my-2" v-for="contact in contacts" :key="contact.id" v-cloak>
            <v-card-title :style="{color: contact.marked ? 'red' : 'black'}">{{contact.name}}</v-card-title>
            <v-list-item two-line>
              <v-list-item-content>
                <div class="overline mb-4">{{contact.lastname}}</div>
                <v-list-item-title class="headline mb-1">{{contact.email}}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
            <v-card-actions> 
              <v-btn text @click="markContact(contact.id)" :disabled="contact.marked">Mark</v-btn>
              <v-btn text @click="removeContact(contact.id)">Delete</v-btn>
            </v-card-actions>
          </v-card>
        </div>
        <p v-else>There are no contacts</p>
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
    },
    contacts: [
      {name: 'Elena', lastname: 'Mus', email: 'rqspopova@gmail.ru', marked: false}
    ],
  }),
  computed: {
    canCreate() {
      return this.form.name && this.form.lastname && this.form.email
    }
  },
  methods: {
    createContact() {
      const {...contact} = this.form;
      this.contacts.push({...contact, id: Date.now()})
      this.form.name = this.form.lastname = this.form.email = ''
    },
    markContact(id) {
      const contact = this.contacts.find(c => {
        return c.id === id
      })
      return contact.marked = true ;
    },
    removeContact(id) {
      this.contacts = this.contacts.filter (c => c.id  !== id)
    },
  },
};
</script>
