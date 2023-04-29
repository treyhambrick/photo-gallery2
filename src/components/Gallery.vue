<template>
  <div>
    <center>
    <div width="60%">
      <p><B><h1 style="font-size:50px; color:blueviolet; margin:10px;">{{title}}</h1></B>
        <BR/>
      {{ description }}
      <BR/>
      <BR/>Contact Trey at <a href="mailto:trey.hambrick@gmail.com?subject='Unit 14'">
        trey.hambrick@gmail.com</a>
    </p>
</div></center>
      <div class="gallery">
        <div class="gallery-panel"
            v-for="photo in photos"
            :key="photo.id">
          <router-link :to="`/photo/${photo.id}`">
            <img :src="thumbUrl(photo.filename)">
          </router-link>
        </div>
  </div>


  </div>
</template>

<script>
import photos from '@/photos.json';

export default {
  name: 'Gallery',
  data() {
    return {
      photos,
      description: 'Club Del Cielo Unit 14 is within a 5-minute walk of Jaco Beach. Guests can take a dip in the outdoor pool or enjoy the many local activities. There is a children\'s pool and in-room conveniences like AC, washers/dryers and refrigerators. Fellow travelers say good things about the pool.',
      title: 'Club Del Cielo Unit 14',
    };
  },
  methods: {
    thumbUrl(filename) {
      return require(`../assets/images/thumbnails/${filename}`);
    },
  },
};
</script>

<style>
  .gallery {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(20rem, 1fr));
    grid-gap: 1rem;
    max-width: 80rem;
    margin: 2rem auto;
    padding: 0 1rem;
  }

  .gallery-panel img {
    width: 83%;
    height: 49vw;
    object-fit: cover;
    border-radius: 0.75rem;
  }
</style>
