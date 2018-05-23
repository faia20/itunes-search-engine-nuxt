<template>
  <div>
    <h1>Results for {{$route.params.id}}</h1>
    <div v-if="albumExists">
      <div v-for="(album, index) in albumData" :key="index">
        <album-entry
          :title="album.collectionCensoredName"
          :image="album.artworkUrl100"
          :artistName="album.artistName"
          :url="album.artistViewUrl"
        />
      </div>
    </div>
    <div v-else>
      <h2>Could not find album</h2>
    </div>
  </div>
</template>

<script>

import axios from 'axios';
import AlbumEntry from '~/components/AlbumEntry'

export default {
  asyncData({params}) {
    return axios.get(`https://itunes.apple.com/search?term=${params.id}&entity=album`)
    .then((response) => {
      return {albumData: response.data.results}
    });
  },
  components: {
    AlbumEntry
  },
  middleware: 'search',
  computed: {
    albumExists() {
      return this.albumData.length > 0;
    }
  }
}
</script>

<style>
  body {
    background: #f1f1f1;
  }
  h1 {
    padding: 20px;
    font-size: 1.3em;
    color: #444;
  }
</style>
