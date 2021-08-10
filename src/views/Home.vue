<template>
  <v-container>
    <search @change="onSearch"></search>
    <v-row>
      <v-col
        cols="12"
        sm="6"
        md="3"
        >
        <v-row v-for="(item, index) in showedItems" :key="index + item">
          <v-col>
            <v-card
              color="#385F73"
              dark
            >
              <v-card-title class="text-h5">
                <span>{{ item.name }}</span>
                <v-spacer></v-spacer>
                <v-checkbox
                  v-model="item.selected"
                ></v-checkbox>
              </v-card-title>
            </v-card>
          </v-col>
        </v-row>
      </v-col>
      <v-col
        cols="12"
        sm="6"
        md="3"
        >
        <v-row v-for="(item, index) in selectedItems" :key="index + item">
          <v-col>
            <v-card
              color="#385F73"
              dark
            >
              <v-card-title class="text-h5">
                <span>{{ item.name }}</span>
              </v-card-title>
            </v-card>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import Search from '@/components/Search.vue';

export default {
  name: 'Home',
  components: {
    Search,
  },
  data() {
    return {
      search: '',
      listOfItems: [
        {
          name: 'Banana',
          selected: false,
        },
        {
          name: 'Bananana',
          selected: false,
        },
        {
          name: 'nananana',
          selected: false,
        },
        {
          name: 'Bana',
          selected: false,
        },
        {
          name: 'Apple',
          selected: false,
        },
        {
          name: 'Apple',
          selected: false,
        },
        {
          name: 'Mikan',
          selected: false,
        },
        {
          name: 'Nanas',
          selected: false,
        },
      ],
    };
  },
  methods: {
    onSearch($event) {
      console.log({ $event });
      this.search = $event;
    },
  },
  computed: {
    showedItems() {
      if (this.search) {
        return this.listOfItems.filter((item) => item.name.includes(this.search));
      }
      return this.listOfItems;
    },
    selectedItems() {
      return this.listOfItems.filter((item) => item.selected);
    },
  },
};
</script>
