<template>
  <v-card
    class="mx-auto"
    max-width="300"
    tile
  >
    <v-list dense>
      <v-subheader>CATEGORIES</v-subheader>
      <v-list-item-group
        v-model="selectedItem"
        color="primary"
      >
        <v-list-item
          v-for="(category, i) in categories"
          :key="i"
        >
          <v-list-item-icon>
            <v-icon>mdi-brush</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{category.name}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-card>
</template>

<script>
  export default {
    data: () => ({
      selectedItem: 1,
      loading: false,
      categories: [],
    }),
    async created(){
      this.loading = true
        try {
          /** get categories */
          const categories= (await this.$axios.get('/categories')).data
          this.categories = categories
        } catch (error) {
          console.log(error)
        }
        this.loading = false
    },
  }
</script>
