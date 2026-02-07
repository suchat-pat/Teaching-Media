<template>
  <v-container class="py-8">
    <v-row justify="center">
      <v-col cols="12" md="10">
        <v-card color="pink-darken-3" theme="dark" class="pa-6 mb-8 text-center" elevation="6">
          <v-icon size="64" class="mb-4">mdi-music-clef-treble</v-icon>
          <h1 class="text-h3 font-weight-bold mb-2">เทคนิคการจำด้วยบทเพลง</h1>
          <p class="text-subtitle-1">เรียนรู้คณิตศาสตร์และคอมพิวเตอร์ผ่านเสียงเพลง สนุกและจำแม่น!</p>
        </v-card>
      </v-col>
    </v-row>

    <v-row justify="center">
      <v-col cols="12" md="8">
        
        <v-card v-for="(song, index) in songs" :key="index" class="mb-6 rounded-xl song-card" elevation="3" border>
          <div class="d-flex flex-no-wrap justify-space-between">
            
            <div class="w-100 pa-4">
              <div class="d-flex align-center mb-2">
                <v-avatar color="pink-lighten-4" size="50" class="mr-4">
                  <span class="text-h6 font-weight-bold text-pink-darken-4">{{ index + 1 }}</span>
                </v-avatar>
                <div>
                  <v-card-title class="text-h6 font-weight-bold text-pink-darken-4 pa-0">
                    {{ song.title }}
                  </v-card-title>
                  <v-card-subtitle class="pa-0 text-caption">
                    {{ song.subtitle }}
                  </v-card-subtitle>
                </div>
              </div>

              <div class="mt-4 mb-2">
                <audio controls class="w-100 custom-audio">
                  <source :src="song.src" type="audio/mpeg">
                  Your browser does not support the audio element.
                </audio>
              </div>

              <div class="mt-2">
                <v-btn 
                  variant="text" 
                  color="grey-darken-1" 
                  class="px-0 text-capitalize"
                  @click="song.showLyrics = !song.showLyrics"
                >
                  <v-icon start>
                    {{ song.showLyrics ? 'mdi-chevron-up' : 'mdi-text-box-outline' }}
                  </v-icon>
                  {{ song.showLyrics ? 'ซ่อนเนื้อเพลง' : 'ดูเนื้อเพลง / เทคนิคการจำ' }}
                </v-btn>

                <v-expand-transition>
                  <div v-show="song.showLyrics">
                    <div class="mt-2 text-body-2 bg-pink-lighten-5 pa-4 rounded text-pink-darken-4">
                       <div style="white-space: pre-line;">{{ song.lyrics }}</div>
                    </div>
                  </div>
                </v-expand-transition>
              </div>

            </div>

            <v-avatar class="ma-3 hidden-sm-and-down" size="125" rounded="0">
              <v-icon size="80" :color="song.color">mdi-{{ song.icon }}</v-icon>
            </v-avatar>
          </div>
        </v-card>

      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref } from 'vue';

const songs = ref([
  {
    title: "หน่วยที่ 1: ระบบจำนวนจริง",
    subtitle: "สมบัติของจำนวนจริงและการแยกตัวประกอบ",
    src: "/songs/unit1-real-number.mp3",
    icon: "math-compass",
    color: "primary",
    showLyrics: false, // [สำคัญ] ต้องเพิ่มตัวแปรนี้เพื่อคุมการเปิดปิดรายตัว
    lyrics: "จำนวนจริงมีตรรกยะ และอตรรกยะปนกันไป...\n(เนื้อเพลงช่วยจำสมบัติปิด สลับที่ เปลี่ยนกลุ่ม)\n..."
  },
  {
    title: "หน่วยที่ 2: ระบบเลขฐาน",
    subtitle: "ฐานสอง ฐานแปด ฐานสิบ ฐานสิบหก",
    src: "/songs/unit2-number-systems.mp3",
    icon: "numeric",
    color: "teal",
    showLyrics: false,
    lyrics: "ฐานสองมีแค่ 0 กับ 1... คอมพิวเตอร์ซึ้งใจใช้อยู่ประจำ\nฐานแปด 0 ถึง 7 จำให้แม่นยำ..."
  },
  {
    title: "หน่วยที่ 3: การคำนวณเลขฐาน",
    subtitle: "การบวก ลบ คูณ หาร และคอมพลีเมนต์",
    src: "/songs/unit3-calculation.mp3",
    icon: "calculator",
    color: "indigo",
    showLyrics: false,
    lyrics: "1 บวก 1 ได้ 0 ทด 1 จำให้ดี...\nลบไม่ได้ต้องยืมหลักหน้ามา (ยืมมาเท่ากับฐาน)..."
  },
  {
    title: "หน่วยที่ 4: ตรรกศาสตร์",
    subtitle: "ประพจน์ ตัวเชื่อม และสัจนิรันดร์",
    src: "/songs/unit4-logic.mp3",
    icon: "head-lightbulb",
    color: "deep-purple",
    showLyrics: false,
    lyrics: "และ จริง เมื่อจริงทั้งคู่... หรือ เท็จ เมื่อเท็จทั้งคู่...\nถ้าแล้ว เท็จกรณีเดียว คือ หน้าจริง หลังเท็จ..."
  },
  {
    title: "หน่วยที่ 5: พีชคณิตบูลีน",
    subtitle: "AND OR NOT และการลดรูปวงจร",
    src: "/songs/unit5-boolean.mp3",
    icon: "gate-and",
    color: "orange",
    showLyrics: false,
    lyrics: "A คอน A ได้ A... A บวก A ก็ได้ A...\nDe Morgan จำง่ายๆ เปลี่ยนเครื่องหมาย แยกบาร์..."
  },
  {
    title: "หน่วยที่ 6: เมทริกซ์",
    subtitle: "การคูณ ดีเทอร์มิแนนต์ และอินเวอร์ส",
    src: "/songs/unit6-matrix.mp3",
    icon: "matrix",
    color: "cyan",
    showLyrics: false,
    lyrics: "คูณเมทริกซ์ แถวคูณหลัก... บวกกันให้ครบสูตร\nDet สองคูณสอง คูณลงลบด้วยคูณขึ้น..."
  },
  {
    title: "Test Song 1",
    subtitle: "Test Subtitle 1",
    src: "/songs/Her.mp3",
    icon: "test-tube",
    color: "error",
    showLyrics: false,
    lyrics: "This is a test song lyric 1...\nLine 2 of the lyrics...\nLine 3 of the lyrics..."
  },
]);
</script>

<style scoped>
.custom-audio {
  height: 40px;
  border-radius: 20px;
  outline: none;
}

.song-card {
  transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
  /* เพิ่ม will-change เพื่อบอก Browser ให้เตรียม render การเคลื่อนไหว */
  will-change: transform, box-shadow; 
}

.song-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 16px rgba(0,0,0,0.12) !important;
}
</style>