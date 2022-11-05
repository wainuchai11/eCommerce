<template>
  <v-card rounded class="pa-md-10 pa-5 text-center" color="primary" dark>
    <h2 class="text-md-h3">Newsletter</h2>
    <p class="text-md-h6 mt-5">Subcribe to receive discounts & more!</p>
    <br />
    <v-sheet color="transparent" class="mx-auto" max-width="400">
      <v-text-field label="Email" type="email" outlined v-model="email">
      </v-text-field>
      <v-btn @click="submit" outlined min-height="50" block>Subcribe</v-btn>
    </v-sheet>
  </v-card>
</template>

<script>
export default {
  data() {
    return {
      email: null,
    };
  },
  methods: {
    async submit() {
      await this.$swal({
        title: "Thank you for subcribing",
        icon: "success",
        allowOutsideCluck: false,
        allowEscapeKey: false,
        timer: 4000,
        timeProgressBar: true,
        showConfirmButton: false,
        text: "You will be notified when we have a deal or item on sale",
      });
    },
  },
};
</script>

<style>
</style>