<template>
    <v-form>
        <v-container>
            <v-row class="text-center">
                <v-col cols="12" lg="1"></v-col>
                <v-col cols="12" lg="4">
                    <v-text-field label="Username" outlined required></v-text-field>
                </v-col>
                <v-col cols="12" lg="4">
                    <v-text-field label="Password" outlined required></v-text-field>
                </v-col>
                <v-col cols="12" lg="2">
                    <v-btn color="success" x-large>Iniciar Sesión</v-btn>
                </v-col>
                <v-col cols="12" lg="1"></v-col>
            </v-row>
            <v-row class="text-md-right text-center">
                <v-col cols="12" lg="9">
                    <v-btn color>Olvidaste tu contraseña</v-btn>
                </v-col>
                <v-col cols="12" lg="3"></v-col>
            </v-row>
        </v-container>
    </v-form>
</template>

<script>
  export default {
    data: () => ({
      valid: false,
      firstname: '',
      lastname: '',
      nameRules: [
        v => !!v || 'Name is required',
        v => v.length <= 10 || 'Name must be less than 10 characters',
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid',
      ],
    }),
  }
</script>