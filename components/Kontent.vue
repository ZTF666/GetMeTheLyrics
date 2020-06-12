<template>
  <div>
    <v-form @submit.prevent="getLyrics()">
      <v-container>
        <v-layout row wrap class="d-flex justify-center">
          <v-flex xs8 sm6 md6>
            <v-row>
              <v-col cols="12" sm="6" md="6">
                <v-text-field
                  label="Artist"
                  outline
                  v-model="artist"
                  aria-autocomplete="false"
                ></v-text-field>
              </v-col>
              <v-col cols="12" sm="6" md="6">
                <v-text-field
                  label="Song"
                  outline
                  v-model="song"
                  aria-autocomplete="false"
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row class="d-flex justify-center">
              <div>
                <v-col>
                  <v-btn @click.prevent="getLyrics()">Get Lyrics</v-btn>
                </v-col>
              </div>
            </v-row>
          </v-flex>
          <!-- radio -->

          <!-- end radio -->
        </v-layout>
      </v-container>
    </v-form>
    <v-card class="mx-auto mb-10" color="black" dark max-width="1000">
      <v-card-title class="justify-center">
        <v-icon large left>mdi-disc</v-icon>
        <span class="headline font-weight-light txt">{{ artist }}</span>
        <v-icon large right>mdi-disc</v-icon>
      </v-card-title>

      <v-card-text class="font-weight-bold">
        <pre class="txt"><center> <strong> {{lyrics}} </strong> </center></pre>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
import axios from 'axios'
var request = new XMLHttpRequest()
export default {
  data() {
    return {
      artist: '',
      song: '',
      lyrics: ''
    }
  },
  methods: {
    async getLyrics() {
      try {
        if (this.artist != null && this.song != null) {
          let response = await axios.get(
            `https://api.lyrics.ovh/v1/` + this.artist + `/` + this.song
          )
          console.log(response)
          let FormattedData = JSON.parse(JSON.stringify(response))
          if (FormattedData.data.lyrics == '') {
            this.lyrics = `Sorry but these lyrics aren't yet added in the database`
          } else {
            this.lyrics = FormattedData.data.lyrics
          }
        }
      } catch (e) {
        this.lyrics =
          'The song / artist does not exist or there is a typo somewhere ! please check'
      }
    }
  }
}
</script>
<style scoped>
.txt {
  color: white;
  font-family: 'Courier New', Courier, monospace;
}
</style>
