<template>
  <v-row class="">
    <v-col
      cols="12"
      sm="6"
      md="3"
      >
      <v-card
        color="#385F73"
        dark
      >
        <v-card-text>
          <v-text-field label="search" v-model="search"></v-text-field>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      search: '',
    };
  },
  watch: {
    search: {
      handler() {
        this.$emit('change', this.search);
      },
    },
  },
};
</script>

<style lang="scss" scoped>

</style>
