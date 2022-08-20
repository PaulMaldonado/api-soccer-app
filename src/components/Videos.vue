<template>
  <div>
      <div class="container mt-4">
          <h1 class="text-center display-4 text-dark fw-bold mt-3">Videos más recientes</h1>
          <div class="row">
              <div class="col-md-4 col-sm-12 col-lg-4 col-xl-4 col-xxl-4 mt-4" v-for="video in videos" :key="video.id">
                <div class="card shadow-lg">
                    <img :src="video.thumbnail" :alt="video.thumbnail" class="card-img-top img-fluid">

                    <div class="card-body">
                        <h5 class="card-title">
                            {{ video.title }}
                        </h5>

                        <p class="card-text">
                            {{ video.competition.name }} - {{ getDateVideo(video.date) }}
                        </p>

                        <div class="d-grid gap-2">
                           <router-link :to="{ name: 'DetailVideo', params: { id: video.competition.id } }" class="btn btn-primary">
                            Ver más
                           </router-link>
                        </div>
                    </div>
                </div>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
import axios from 'axios'
import moment from 'moment'

export default {
    name: 'Videos',

    data() {
        return {
            videos: [],
        }
    },

    mounted() {
        this.showVideos();
    },

    methods: {
        showVideos() {
            axios({
                method: 'GET',
                url: 'https://free-football-soccer-videos.p.rapidapi.com/',
                headers: {
                    'X-RapidAPI-Key': '5ae9e6c3e8mshee189598f5d2334p1b32b2jsn48e806bb90b5',
                    'X-RapidAPI-Host': 'free-football-soccer-videos.p.rapidapi.com'
                }
            })
            .then(response => {
                console.log(response)
                this.videos = response.data;
            })
            .catch(error => {
                console.error(error);
            })
        },

        getDateVideo(date) {
            return moment(date, 'YYYY-MM-DD').format('DD/MM/YYYY')
        }
    }
}
</script>

<style scoped>

</style>