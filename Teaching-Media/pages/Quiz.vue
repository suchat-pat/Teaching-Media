<template>
  <v-container class="py-8">
    <v-row justify="center">
      <v-col cols="12" md="10">
        <v-card color="deep-purple-accent-4" theme="dark" class="pa-6 mb-8 text-center" elevation="8">
          <v-icon size="64" class="mb-4">mdi-school-outline</v-icon>
          <h1 class="text-h3 font-weight-bold mb-2">คลังแบบทดสอบ</h1>
          <p class="text-subtitle-1 text-grey-lighten-2">
            ทดสอบความรู้ความเข้าใจในแต่ละหน่วยการเรียนรู้ (Total 6 Units)
          </p>
        </v-card>
      </v-col>
    </v-row>

    <v-row justify="center">
      <v-col cols="12" md="10">
        <v-row>
          <v-col 
            v-for="(unit, index) in quizUnits" 
            :key="index" 
            cols="12" 
            sm="6" 
            md="4"
          >
            <v-card 
              class="mx-auto h-100 d-flex flex-column transition-swing"
              elevation="4"
              rounded="lg"
              hover
              border
            >
              <div :class="`bg-${unit.color}-lighten-5 pa-4 text-center`">
                <v-avatar :color="unit.color" size="80" variant="flat">
                  <v-icon size="48" color="white">{{ unit.icon }}</v-icon>
                </v-avatar>
              </div>

              <v-card-item>
                <div class="text-overline mb-1 text-grey-darken-1">
                  {{ unit.subtitle }}
                </div>
                <div class="text-h6 font-weight-bold mb-2">
                  {{ unit.title }}
                </div>
                <div class="text-body-2 text-grey-darken-1">
                  {{ unit.description }}
                </div>
              </v-card-item>

              <v-spacer></v-spacer>

              <v-divider></v-divider>

              <v-card-actions class="pa-4 bg-grey-lighten-5">
                <v-btn 
                  :color="unit.color" 
                  variant="flat" 
                  block 
                  size="large"
                  :href="unit.link"
                  target="_blank"
                  prepend-icon="mdi-pencil-box-outline"
                >
                  ทำแบบทดสอบ
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref } from 'vue';

// ข้อมูลแบบทดสอบแต่ละหน่วย
// *หมายเหตุ: คุณสามารถเปลี่ยน property 'link' เป็น URL จริงๆ ของ Google Form หรือหน้าเว็บที่คุณต้องการลิ้งค์ไป
const quizUnits = ref([
  {
    title: "ระบบจำนวนจริง",
    subtitle: "หน่วยที่ 1",
    description: "ทดสอบเรื่องสมบัติจำนวนจริง, การแยกตัวประกอบ และอสมการ",
    icon: "mdi-math-compass",
    color: "blue",
    link: "https://wayground.com/join/pre-game/running/U2FsdGVkX1%252BDTJH4NEPl%252BT5gMi3PybQjG49cfphbMv1T2P%252B23xh%252FGQ%252FDsnX9fN8STP8NPcEG7UgPW%252BIIz882oQuDo3xcK7vhvkIUGD42SjQnjqlmdGJ7fm%252BM5G8FlnVBAW%252BZZ6tognpG0XCV9O1Q4Z3aJzWi0Px5lAwBSUGvYvk%253D/start" // ใส่ลิงก์จริงตรงนี้
  },
  {
    title: "ระบบเลขฐาน",
    subtitle: "หน่วยที่ 2",
    description: "ทดสอบการเปลี่ยนฐานเลข ฐานสอง ฐานแปด ฐานสิบ ฐานสิบหก",
    icon: "mdi-numeric",
    color: "teal",
    link: "https://wayground.com/join/pre-game/running/U2FsdGVkX19ff9mFGYgZf7j3ifBvLXX74SL9TPqx1I0GgfFZNGkQpAdLgMd2jCNwZg%252B9PeTgt4Cgjrb0Md6evdeluLVfx8UYHnTW5GgipoCMmvbc6i%252Bf0NpL7lKt8GTQEgSH9VJcEHhNXYSv6EW5mjEF93uKpdy9onsKqq8kj8Y%253D/start"
  },
  {
    title: "การคำนวณเลขฐาน",
    subtitle: "หน่วยที่ 3",
    description: "ทดสอบการบวก ลบ คูณ หาร และการใช้คอมพลีเมนต์",
    icon: "mdi-calculator",
    color: "cyan",
    link: "https://share.google/9iczfrXKPPnV4DVDz"
  },
  {
    title: "ตรรกศาสตร์",
    subtitle: "หน่วยที่ 4",
    description: "ทดสอบค่าความจริง, สัจนิรันดร์ และการอ้างเหตุผล",
    icon: "mdi-lightbulb-on",
    color: "purple",
    link: "https://share.google/Hs3Cs9HDWF0x5HtDu"
  },
  {
    title: "พีชคณิตบูลีน",
    subtitle: "หน่วยที่ 5",
    description: "ทดสอบกฎของบูลีน, การลดรูปวงจร และ Logic Gates",
    icon: "mdi-gate-and",
    color: "orange",
    link: "https://share.google/P9AdX5ATE3xcAgo5B"
  },
  {
    title: "เมทริกซ์",
    subtitle: "หน่วยที่ 6",
    description: "ทดสอบการคูณเมทริกซ์, ดีเทอร์มิแนนต์ (Det) และอินเวอร์ส",
    icon: "mdi-matrix",
    color: "deep-orange",
    link: "https://share.google/M69cFNdastUwNLXk5"
  }
]);
</script>

<style scoped>
/* เพิ่ม Effect ให้การ์ดเด้งขึ้นเล็กน้อยเมื่อเอาเมาส์ไปวาง */
.v-card {
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
}

.v-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0,0,0,0.15) !important;
}
</style>