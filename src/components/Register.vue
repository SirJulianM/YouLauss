<template>
    <v-container>
        <v-row>
            <v-col cols="12" lg="3"></v-col>
            <v-col cols="12" lg="3" class="text-lg-left text-center">
                <h2>Crear cuenta</h2>
            </v-col>
            <v-col cols="12" lg="3" class="text-lg-right text-center">
                <h2>YouLauss</h2>
            </v-col>
            <v-col cols="12" lg="3"></v-col>
        </v-row>
        <v-row class="text-center">
            <v-col cols="12" lg="3"></v-col>
            <v-col cols="12" lg="6">
                <v-text-field label="Username" :rules="[rules.required, rules.max, rules.names]" counter outlined required></v-text-field>
            </v-col>
            <v-col cols="12" lg="3"></v-col>
        </v-row>
        <v-row class="text-center">
            <v-col cols="12" lg="3"></v-col>
            <v-col cols="12" lg="3">
                <v-text-field label="First Name" :rules="[rules.required, rules.max]" counter outlined required></v-text-field>
            </v-col>
            <v-col cols="12" lg="3">
                <v-text-field label="Last Name" :rules="[rules.required, rules.max]" counter outlined required></v-text-field>
            </v-col>
            <v-col cols="12" lg="3"></v-col>
        </v-row>
        <v-row class="text-center">
            <v-col cols="12" lg="3"></v-col>
            <v-col cols="12" lg="3">
                <v-text-field label="Clave" :rules="[rules.required, rules.min, rules.upper, rules.num, rules.chara]" :type="show ? 'text' : 'password'" :append-icon="show ? 'mdi-eye' : 'mdi-eye-off'" counter outlined @click:append="show = !show"></v-text-field>
            </v-col>
            <v-col cols="12" lg="3">
                <v-text-field label="Verificar Clave" :rules="[rules.required, rules.min, rules.upper, rules.num, rules.chara]" :type="vshow ? 'text' : 'password'" :append-icon="vshow ? 'mdi-eye' : 'mdi-eye-off'" counter outlined @click:append="vshow = !vshow"></v-text-field>
            </v-col>
            <v-col cols="12" lg="3"></v-col>
        </v-row>
        <v-row class="text-center">
            <v-col cols="12" lg="3"></v-col>
            <v-col cols="12" lg="6">
                <v-text-field label="Celular" outlined required></v-text-field>
            </v-col>
            <v-col cols="12" lg="3"></v-col>
        </v-row>
        <v-row class="text-center text-lg-right">
            <v-col cols="12" lg="3"></v-col>
            <v-col cols="12" lg="6">
                <v-btn color="success">Registrate</v-btn>
            </v-col>
            <v-col cols="12" lg="3"></v-col>
        </v-row>
        <v-row class="text-center">
            <v-col cols="12" lg="3"></v-col>
            <v-col cols="12" lg="2">
                Ayuda
            </v-col>
            <v-col cols="12" lg="2">
                Privacidad
            </v-col>
            <v-col cols="12" lg="2">
                Condiciones
            </v-col>
            <v-col cols="12" lg="3"></v-col>
        </v-row>
    </v-container>
</template>

<script>
  export default {
    data () {
      return {
        show: false,
        vshow: false,
        noValid: ['123', '666', 'abc', 'admin', 'root', 'admon', 'Lucifer', 'Dios', 'Zeus', 'Demon'],
        password: 'Password',
        rules: {
          required: value => !!value || 'Required.',
          min: v => v.length >= 10 || 'Min 10 characters',
          max: v => v.length <=25 || 'Max 25 characters',
          upper: v =>  v.match(/[A-Z]/) || 'An uppercase letter',
          num: v => v.match(/[0-9]/) || 'A number',
          chara: v => v.match(/[@#$%^&*-_/+']/) || 'A special character',
          names: v => v.includes(!noValid) || 'Name no valid'
        },
      }
    },
  }
</script>

<style>

</style>