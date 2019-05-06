<template>
    <v-container class="pa-0">
        <v-layout wrap align-center justify-center row fill-height >
           <v-flex xs12 md3 lg3 class="pa-2">
               <p class="google-font" style="font-size:180%">Qué hacemos?</p>
               <p class="google-font" style="font-size:110%">Los Google Developer Groups (GDGs) son para desarrolladores que estén interesados en la tecnología de desarrollo de Google.</p>

               <p class="google-font" style="font-size:110%">Estas son algunas de ellas</p>

                <span v-for="(item,i) in whatWeDoData" :key="i">
                    <v-tooltip bottom>
                        <template v-slot:activator="{ on }" >
                            <a :href="item.link" target="_blank" flat class="ma-0">
                                <img :src="getImgUrl(item.image)" width="30vh" alt="" srcset="" dark v-on="on">
                            </a>
                            &nbsp;&nbsp;&nbsp;
                        </template>
                        <span>{{item.TechName}}</span>
                    </v-tooltip>
                </span>

                <br><br>

                <v-btn :href="chapterDetails.GDGProgramWebsite" outline target="_blank" round color="cyan" style="text-transform: capitalize;border-radius:5px;text-transform: capitalize;" flat  class="ml-0 google-font hidden-md-and-down" dark>Conocer más</v-btn>

            </v-flex>
            <v-flex xs12 md9 lg9 class="">
                <v-layout row wrap>

                    <v-flex xs6 sm6 md3 lg3 class="text-xs-center pa-2">
                        <v-icon large style="font-size:300%">chat_bubble</v-icon>
                        <p class="google-font" style="font-size:130%">Charlas</p>
                        <p class="google-font" style="font-size:110%">Platicamos sobre desarrollo tecnológico y el uso de herramientas.</p>
                    </v-flex>

                    <v-flex xs6 sm6 md3 lg3 class="text-xs-center pa-2">
                        <v-icon large style="font-size:300%">code</v-icon>
                        <p class="google-font" style="font-size:130%">Codelabs</p>
                        <p class="google-font" style="font-size:110%">Práctica y obten orientación de los miembros de la comunidad.</p>
                    </v-flex>

                    <v-flex xs6 sm6 md3 lg3 class="text-xs-center pa-2">
                        <v-icon large style="font-size:300%">school</v-icon>
                        <p class="google-font" style="font-size:130%">Formación</p>
                        <p class="google-font" style="font-size:110%">Compartir conocimientos en diferentes empresas, colegios y universidades.</p>
                    </v-flex>

                    <v-flex xs6 sm6 md3 lg3 class="text-xs-center pa-2">
                        <v-icon large style="font-size:300%">airplay</v-icon>
                        <p class="google-font" style="font-size:130%">En Vivo</p>
                        <p class="google-font" style="font-size:110%">Nos reunimos para retransmitir eventos y compartir el conocimiento.</p>
                    </v-flex>

                </v-layout>
            </v-flex>
        </v-layout>

    </v-container>
</template>

<script>
import whatWeDoData from '@/assets/data/whatWeDoComponentData.json'
import ChapterDetails from '@/assets/data/chapterDetails.json'
export default {
    data() {
        return {
            chapterDetails: ChapterDetails,
            whatWeDoData: whatWeDoData
        }
    },
    methods:{
        getImgUrl(pic) {
            if(pic.length>0){
                return require('@/assets/img/what-we-do/'+pic)
            }else{
                return require('@/assets/img/what-we-do/notFound.png')
            }
        },
    }
}
</script>
