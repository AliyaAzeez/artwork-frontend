<template>
  <div>
    <div v-for="painting in paintings" :key="painting.index">
      <painting
        :painting="painting"/>

    </div>
  </div>
</template>
<script>
import painting from '@/components/painting/painting'
export default {
   data(){
    return {
      paintings: [],
      loading: false,
    }
  },
  components: {
    painting
  },
  async created(){
    this.getAllPaintings()
  },
  methods:{
    async getAllPaintings() {
      this.loading = true
      try {
        /** get paintings */
        const paintings= (await this.$axios.get('/paintings')).data
        this.paintings = paintings
      } catch (error) {
        console.log(error)
      }
    this.loading = false
  }
}
}
</script>
