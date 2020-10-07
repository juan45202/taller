<template>
    <v-form v-model="formUsers">
        <v-container>
          <v-row>
            <v-col
              cols="12"
              md="4"
            >
              <v-text-field
                v-model="user.firstname"
                :rules="fieldRequired"
                :counter="10"
                label="First name"
                required
              ></v-text-field>
            </v-col>

            <v-col
              cols="12"
              md="4"
            >
              <v-text-field
                v-model="user.lastname"
                :rules="fieldRequired"
                :counter="10"
                label="Last name"
                required
              ></v-text-field>
            </v-col>

            <v-col
              cols="12"
              md="4"
            >
              <v-text-field
                v-model="user.email"
                :rules="emailRules"
                label="E-mail"
                required
              ></v-text-field>
            </v-col>
          </v-row>
        </v-container>
    </v-form>

</template>

<script>
  export default {
    data() {
        return{
            formUsers: null,
            user: {
                identification_type: null,
                identification: null,
                firstname: null,
                lastname: null,
                password: null,
                email: null,
                accepted: null,
                rol: null,
            },
            
            fieldRequired: [
                (v) => !!v || 'Field is required',
            ],

            email: '',
            emailRules: [
              v => !!v || 'E-mail is required',
              v => /.+@.+/.test(v) || 'E-mail must be valid',
            ],
        }
    },
  }
</script>