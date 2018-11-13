<template>
  <div>
    <input type="text" placeholder="Add Band.." v-model="bandName" @keypress.enter = "addBand">
    <button @click  = "addBand"> Add </button>

    <ul>
      <BandItem v-for="band in bands" :key="band.id" :band="band">
        {{band.name}}
      </BandItem>
    </ul>
  </div>
</template>


<script>
import BandItem from '@/components/BandItem.vue'

export default {
  name: 'BandList',
  components: {
    BandItem
  },
  data () {
    return {
      id: 3,
      bandName:'',
      bands: [{
        id: 1,
        name: 'Black Sabbath',
        songs: ['Iron Man', 'War Pigs']
      }, {
        id: 2,
        name: 'ColdPlay',
        songs: ['Yellow', 'Fix you', 'Mylo xyloto']
      }]
    }
  },
    methods: {
    addBand () {
      this.bands.push({id: this.id++, name: this.bandName, songs: []})
      this.bandName = ''
  }
    }
}
</script>
