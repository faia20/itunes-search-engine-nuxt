<template>
  <div class="album-entry">
    <div class="image-col">
      <img :src="image" />
    </div>
    <div class="info-col">
      <a :href="url">
        <h2>{{title}}</h2>
        <h3>{{artistName}}</h3>
      </a>
    </div>
    
  </div>
</template>

<script>
  export default {
    props: ['title', 'image', 'artistName', 'url']
  }
</script>

<style scoped>
  a {
    text-decoration: none;
  }
  a h2 {
    color: #444;
    font-size: 1.2em;
  }
  a h3 {
    color: #666;
    font-size: 0.9em;
  }
  .album-entry {
    background: #fff;
    display: table;
    width: 90%;
    margin: auto;
    margin-bottom: 10px;
    box-shadow: 0px 3px 5px 0px rgba(0,0,0,0.1);
    border: 1px solid #f8f8f8;
    color: #444;
    max-width: 600px;
  }

  .image-col,
  .info-col {
    display: table-cell;
    vertical-align: middle;
    text-align: left;
  }

  .image-col {
    width: 100px;
  }

  .info-col {
    padding: 5px 20px;
  }


</style>
