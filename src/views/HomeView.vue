<template>
  <h1>Gif Router</h1>
  <img :src="img" :alt="title" />
</template>

<script>
export default {
  data: () => ({
    img: "",
    title: "",
  }),
  created() {
    this.getRandomGifs();
  },
  methods: {
    async getRandomGifs() {
      const resp = await fetch(
        "https://api.giphy.com/v1/gifs/random?api_key=R8SIbnO8v5TPIzf6fzpFp0mIo7iVLZ0i"
      );
      const { data } = await resp.json();
      this.img = data.images.original.url;
      this.title = data.title;
      console.log(data);
    },
  },
};
</script>
