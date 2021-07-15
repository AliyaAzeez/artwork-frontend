<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <div class="text-center">

      </div>
      <v-card>
        <v-card-title class="headline">
          Welcome to the Art Gallery
        </v-card-title>
        <v-card-text>
          <p>Find the perfect piece of art for you - whatever your taste. Explore our exclusive collection of original paintings and artwork at Art Gallery.</p>


          <p>Thank you for supporting and I look forward to bringing more exciting collections in the future.</p>
          <div class="text-xs-right">
            <em><small>&mdash; Aliya</small></em>
          </div>
          <hr class="my-3">
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn
            color="primary"
            nuxt
            to="/painting"
          >
            Continue
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    Logo,
    VuetifyLogo
  }
}
</script>
