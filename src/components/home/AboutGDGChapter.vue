<template>
    <v-container class="pa-0 white--text">
        <v-layout wrap align-center justify-center row fill-height class="my-3" >
           <v-flex xs12 md10 lg10 class="pa-2">
               <p class="google-font" style="font-size:150%">Acerca de  {{chapterDetails.ChapterName}}</p>
               <p class="google-font" style="font-size:110%">
                   {{chapterDetails.ChapterLongDec}}
               </p>
               <v-btn :href="chapterDetails.ChapterMeetupLink" target="_blank" outline color="white" class="ma-0 google-font" style="border-radius:5px;text-transform: capitalize;">Regístrate en Meetup</v-btn>
               &nbsp;
               <v-btn :href="chapterDetails.socialLinks[0].link" target="_blank" outline color="white" class="ma-0 google-font" style="border-radius:5px;text-transform: capitalize;">Síguenos en Facebook</v-btn>
                <br><br>
               <router-link to="/about" class="google-font" style="text-decoration:none;color:white">Conoce más de  {{chapterDetails.ChapterName}}</router-link>
            </v-flex>
        </v-layout>

    </v-container>
</template>

<script>
import ChapterDetails from '@/assets/data/chapterDetails.json'
export default {
    data() {
        return {
            chapterDetails: ChapterDetails
        }
    },
}
</script>
