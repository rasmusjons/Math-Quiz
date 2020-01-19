<template>
    <div>
        <div>
            <p>{{info}}</p>
            <img :src="info" />
        </div>
    </div>
</template>

<script>
    const axios = require('axios');

export default {

    data() {
        return {
            adress:
                "https:api.giphy.com/v1/gifs/translate?api_key=XrWHvFSmYyE0xfmbS6aSeVz6cCSLn4qx&s=congratz",
            url: "",
            info: null
        };
    },
    mounted() {
        axios.get(this.adress).then(response => (this.info = response.data.data.url))
        .catch(error => console.log(error))
        console.log(this.info)

    }
};
</script>
<style scoped>
</style


/* { "data": 
{ "type": 
"gif", 
"id": "3o6fIUZTTDl0IDjbZS", 
"url": "https://giphy.com/gifs/congratulations-congrats-3o6fIUZTTDl0IDjbZS", 
"slug": "congratulations-congrats-3o6fIUZTTDl0IDjbZS",
"bitly_gif_url": "https://gph.is/2iSJzoy", 
"bitly_url": "https://gph.is/2iSJzoy",
"embed_url": "https://giphy.com/embed/3o6fIUZTTDl0IDjbZS", "username": "", "source": "", "title": "congrats GIF", "rating": "g", "content_url": "", "source_tld": "", "source_post_url": "", "is_sticker": 0, "import_datetime": "2017-11-13 19:53:20", "trending_datetime": "0000-00-00 00:00:00", "images": { "downsized_large": { "height": "370", "size": "440159", "url": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/giphy.gif?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=giphy.gif", "width": "498" }, 
"fixed_height_small_still": { "height": "100", "size": "9711", "url": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/100_s.gif?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=100_s.gif", "width": "135" }, "original": { "frames": "5", "hash": "48b90c5c6f1145cb8b9931384732e3d3", "height": "370", "mp4": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/giphy.mp4?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=giphy.mp4", "mp4_size": "139967", "size": "440159", "url": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/giphy.gif?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=giphy.gif", "webp": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/giphy.webp?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=giphy.webp", "webp_size": "273562", "width": "498" }, "fixed_height_downsampled": { "height": "200", "size": "136459", "url": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/200_d.gif?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=200_d.gif", "webp": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/200_d.webp?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=200_d.webp", "webp_size": "93442", "width": "269" }, "downsized_still": { "height": "370", "size": "98256", "url": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/giphy-downsized_s.gif?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=giphy-downsized_s.gif", "width": "498" }, "fixed_height_still": { "height": "200", "size": "30065", "url": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/200_s.gif?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=200_s.gif", "width": "269" }, "downsized_medium": { "height": "370", "size": "440159", "url": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/giphy.gif?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=giphy.gif", "width": "498" }, "downsized": { "height": "370", "size": "440159", "url": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/giphy-downsized.gif?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=giphy-downsized.gif", "width": "498" }, "preview_webp": { "height": "126", "size": "48910", "url": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/giphy-preview.webp?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=giphy-preview.webp", "width": "170" }, "original_mp4": { "height": "356", "mp4": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/giphy.mp4?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=giphy.mp4", "mp4_size": "139967", "width": "480" }, "fixed_height_small": { "height": "100", "mp4": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/100.mp4?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=100.mp4", "mp4_size": "34031", "size": "42481", "url": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/100.gif?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=100.gif", "webp": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/100.webp?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=100.webp", "webp_size": "32300", "width": "135" }, "fixed_height": { "height": "200", "mp4": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/200.mp4?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=200.mp4", "mp4_size": "53876", "size": "136459", "url": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/200.gif?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=200.gif", "webp": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/200.webp?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=200.webp", "webp_size": "93442", "width": "269" }, "downsized_small": { "height": "332", "mp4": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/giphy-downsized-small.mp4?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=giphy-downsized-small.mp4", "mp4_size": "76676", "width": "446" }, "preview": { "height": "174", "mp4": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/giphy-preview.mp4?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=giphy-preview.mp4", "mp4_size": "31412", "width": "234" }, "fixed_width_downsampled": { "height": "149", "size": "83029", "url": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/200w_d.gif?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=200w_d.gif", "webp": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/200w_d.webp?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=200w_d.webp", "webp_size": "60474", "width": "200" }, "fixed_width_small_still": { "height": "75", "size": "6184", "url": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/100w_s.gif?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=100w_s.gif", "width": "100" }, "fixed_width_small": { "height": "75", "mp4": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/100w.mp4?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=100w.mp4", "mp4_size": "14077", "size": "26760", "url": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/100w.gif?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=100w.gif", "webp": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/100w.webp?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=100w.webp", "webp_size": "20032", "width": "100" }, "original_still": { "height": "370", "size": "98256", "url": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/giphy_s.gif?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=giphy_s.gif", "width": "498" }, "fixed_width_still": { "height": "149", "size": "18293", "url": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/200w_s.gif?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=200w_s.gif", "width": "200" }, "looping": { "mp4": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/giphy-loop.mp4?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=giphy-loop.mp4", "mp4_size": "4174988" }, "fixed_width": { "height": "149", "mp4": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/200w.mp4?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=200w.mp4", "mp4_size": "37436", "size": "83029", "url": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/200w.gif?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=200w.gif", "webp": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/200w.webp?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=200w.webp", "webp_size": "60474", "width": "200" }, "preview_gif": { "height": "118", "size": "49525", "url": "https://media3.giphy.com/media/3o6fIUZTTDl0IDjbZS/giphy-preview.gif?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=giphy-preview.gif", "width": "159" }, "480w_still": { "url": "https://media4.giphy.com/media/3o6fIUZTTDl0IDjbZS/480w_s.jpg?cid=82bcbc73237cc7ecc52ba65a6b064300e0e2a3c53c254c78&rid=480w_s.jpg", "width": "480", "height": "357" } } }, "meta": { "status": 200, "msg": "OK", "response_id": "237cc7ecc52ba65a6b064300e0e2a3c53c254c78" } }
 */
