<template>
  <v-container class="py-8">
    <v-row justify="center">
      <v-col cols="12" md="10">
        <v-card 
          class="mx-auto mb-8 overflow-hidden" 
          elevation="10"
        >
          <v-img
            src="https://images.unsplash.com/photo-1509228468518-180dd4864904?q=80&w=2070&auto=format&fit=crop"
            height="300"
            cover
            gradient="to bottom, rgba(0,0,0,.3), rgba(0,0,0,.7)"
          >
            <div class="d-flex fill-height flex-column justify-end pa-6 text-white">
              <h1 class="text-h3 font-weight-bold mb-2">คณิตศาสตร์คอมพิวเตอร์</h1>
              <h2 class="text-h5 font-weight-light opacity-90">Mathematics for Computer</h2>
              <v-chip label class="mb-3 w-auto" size="large">
                รหัสวิชา 21901-2005
              </v-chip>
            </div>
          </v-img>
        </v-card>
      </v-col>
    </v-row>

    <v-row justify="center">
      <v-col cols="12" md="10">
        <v-row>
          <v-col cols="12" md="8">
            <v-card class="h-100 rounded-lg" elevation="2" border>
              <v-card-item>
                <template v-slot:prepend>
                  <v-avatar color="cyan-lighten-5" size="50">
                    <v-icon color="cyan-darken-3" size="30">mdi-book-open-page-variant</v-icon>
                  </v-avatar>
                </template>
                <v-card-title class="text-h5 font-weight-bold text-cyan-darken-4">
                  คำอธิบายรายวิชา
                </v-card-title>
                <v-card-subtitle>Course Description</v-card-subtitle>
              </v-card-item>
              
              <v-divider class="mx-4"></v-divider>

              <v-card-text class="text-body-1 text-grey-darken-3 leading-relaxed pa-6">
                <p style="line-height: 2; text-indent: 40px;">
                  ศึกษาและปฏิบัติเกี่ยวกับ <strong>ระบบจำนวนจริง</strong> โครงสร้างและสมบัติของจำนวนจริง 
                  <strong>ระบบเลขฐาน</strong> การแปลงเลขฐานสอง ฐานแปด ฐานสิบ และฐานสิบหก 
                  <strong>การคำนวณเลขฐาน</strong> การบวก ลบ คูณ หาร และการคอมพลีเมนต์ 
                  หลักการของ <strong>ตรรกศาสตร์</strong> ประพจน์ การเชื่อมประพจน์ การหาค่าความจริง การอ้างเหตุผลและสัจนิรันดร์ 
                  <strong>พีชคณิตบูลีน</strong> กฎและทฤษฎีบทของบูลีน การลดรูปวงจรลอจิก (Switching Circuit) 
                  และ <strong>เมทริกซ์</strong> ดีเทอร์มิแนนต์ อินเวอร์สการคูณ และการประยุกต์ใช้เมทริกซ์ในการแก้ระบบสมการเชิงเส้น
                </p>
              </v-card-text>
            </v-card>
          </v-col>

          <v-col cols="12" md="4">
            <v-card class="h-100 rounded-lg" elevation="2" color="cyan-darken-3" theme="dark">
              <v-card-item>
                <template v-slot:prepend>
                  <v-icon size="30" class="mr-2">mdi-target</v-icon>
                </template>
                <v-card-title class="font-weight-bold">จุดประสงค์รายวิชา</v-card-title>
              </v-card-item>
              
              <v-card-text class="pt-2">
                <v-list bg-color="transparent" density="comfortable">
                  <v-list-item v-for="(item, i) in objectives" :key="i">
                    <template v-slot:prepend>
                      <v-icon color="cyan-accent-2" size="small" class="mt-1">mdi-check-circle</v-icon>
                    </template>
                    <v-list-item-title class="text-body-2 text-wrap ml-2">
                      {{ item }}
                    </v-list-item-title>
                  </v-list-item>
                </v-list>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>

        <v-row class="mt-4">
          <v-col cols="12">
            <h3 class="text-h5 font-weight-bold text-grey-darken-3 mb-4 d-flex align-center">
              <v-icon color="cyan-darken-3" class="mr-2">mdi-layers-triple</v-icon>
              หัวข้อการเรียนรู้ (Topics)
            </h3>
          </v-col>
          
          <v-col v-for="(topic, index) in topics" :key="index" cols="12" sm="6" md="4">
            <v-hover v-slot="{ isHovering, props }">
              <v-card 
                v-bind="props"
                :elevation="isHovering ? 6 : 1"
                class="transition-swing rounded-lg border-s-lg"
                :class="`border-${topic.color}`"
                :style="`border-left-width: 6px !important;`"
              >
                <v-card-item>
                  <div class="text-overline mb-1" :class="`text-${topic.color}`">
                    Unit {{ index + 1 }}
                  </div>
                  <div class="text-h6 font-weight-bold mb-1">
                    {{ topic.title }}
                  </div>
                  <div class="text-caption text-grey-darken-1">
                    {{ topic.desc }}
                  </div>
                </v-card-item>
              </v-card>
            </v-hover>
          </v-col>
        </v-row>

        <v-row class="mt-8">
          <v-col cols="12">
            <h3 class="text-h5 font-weight-bold text-grey-darken-3 mb-4 d-flex align-center">
              <v-icon color="cyan-darken-3" class="mr-2">mdi-clipboard-check-outline</v-icon>
              เกณฑ์การวัดและประเมินผล
            </h3>
          </v-col>

          <v-col cols="12" md="6">
            <v-card class="rounded-lg h-100" elevation="2" border>
              <v-card-title class="bg-grey-lighten-4 py-3 font-weight-bold text-subtitle-1">
                สัดส่วนคะแนน (100 คะแนน)
              </v-card-title>
              <v-divider></v-divider>
              <v-list lines="two">
                <v-list-item>
                  <template v-slot:prepend>
                    <v-avatar color="blue-lighten-5" size="40">
                      <v-icon color="blue-darken-2">mdi-account-star</v-icon>
                    </v-avatar>
                  </template>
                  <v-list-item-title class="font-weight-bold text-blue-darken-2">1. จิตพิสัย</v-list-item-title>
                  <template v-slot:append>
                    <span class="text-h6 font-weight-bold text-blue-darken-2">20</span>
                    <span class="ml-1 text-caption">คะแนน</span>
                  </template>
                </v-list-item>

                <v-divider inset></v-divider>

                <v-list-item>
                  <template v-slot:prepend>
                    <v-avatar color="teal-lighten-5" size="40">
                      <v-icon color="teal-darken-2">mdi-notebook-edit</v-icon>
                    </v-avatar>
                  </template>
                  <v-list-item-title class="font-weight-bold text-teal-darken-2">2. คะแนนระหว่างภาค</v-list-item-title>
                  <v-list-item-subtitle>
                    แบบทดสอบ(20), แบบฝึกหัด(10), ประเมินผลงาน(10)
                  </v-list-item-subtitle>
                  <template v-slot:append>
                    <span class="text-h6 font-weight-bold text-teal-darken-2">40</span>
                    <span class="ml-1 text-caption">คะแนน</span>
                  </template>
                </v-list-item>

                <v-divider inset></v-divider>

                <v-list-item>
                  <template v-slot:prepend>
                    <v-avatar color="deep-purple-lighten-5" size="40">
                      <v-icon color="deep-purple-darken-2">mdi-file-document-edit</v-icon>
                    </v-avatar>
                  </template>
                  <v-list-item-title class="font-weight-bold text-deep-purple-darken-2">3. คะแนนสอบ</v-list-item-title>
                  <v-list-item-subtitle>กลางภาค (20), ปลายภาค (20)</v-list-item-subtitle>
                  <template v-slot:append>
                    <span class="text-h6 font-weight-bold text-deep-purple-darken-2">40</span>
                    <span class="ml-1 text-caption">คะแนน</span>
                  </template>
                </v-list-item>
              </v-list>
            </v-card>
          </v-col>

          <v-col cols="12" md="6">
            <v-card class="rounded-lg h-100" elevation="2" border>
              <v-table density="comfortable">
                <thead class="bg-grey-lighten-4">
                  <tr>
                    <th class="text-left font-weight-bold">ช่วงคะแนน</th>
                    <th class="text-center font-weight-bold">ระดับคะแนน (เกรด)</th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for="grade in gradingScale" :key="grade.range">
                    <td>{{ grade.range }}</td>
                    <td class="text-center">
                      <v-chip 
                        :color="grade.score >= 3 ? 'green-darken-1' : grade.score >= 1 ? 'orange-darken-1' : 'red-darken-1'" 
                        size="small" 
                        label 
                        class="font-weight-bold"
                      >
                        {{ grade.score }}
                      </v-chip>
                    </td>
                  </tr>
                </tbody>
              </v-table>
            </v-card>
          </v-col>
        </v-row>
        
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref } from 'vue';

const objectives = ref([
  "เข้าใจเกี่ยวกับระบบจํานวน ระบบเลขฐาน ตรรกะศาสตร์เบื้องต้น พีชคณิตบูลีน ดีเทอร์มิแนนซ์ เมทริกซ์พีชคณิตเชิงเส้น เซ็ตและฟังก์ชัน",
  "มีทักษะในการคํานวณทางคณิตศาสตร์คอมพิวเตอร์",
  "มีคุณธรรม จริยธรรมและเจตคติที่ดีในการใช้คณิตศาสตร์คอมพิวเตอร์",
  "เพื่อให้มีกิจนิสัยที่ดีในการคิดวิเคราะห์อย่างเป็นระบบ"
]);

const topics = ref([
  { title: "ระบบจำนวนจริง", desc: "จํานวนจริง ,การบวกจํานวนจริง ,การคูณจํานวนจริง ,การเท่ากันในระบบจํานวนจริง", color: "blue" },
  { title: "ระบบเลขฐาน", desc: "ระบบเลขฐานที่ใช้ในคอมพิวเตอร์ ,ระบบเลขฐานสิบ ,ระบบเลขฐานสอง ,ระบบเลขฐานแปด ,ระบบเลขฐานสิบหก", color: "teal" },
  { title: "การคำนวณเลขฐาน", desc: "การแปลงเลขฐานสอง เลขฐานแปด เลขฐานสิบ หกเป็นเลขฐานสิบ ,การแปลงเลขฐานสิบเป็นเลขฐานสอง เลขฐาน แปดและเลขฐานสิบหก ,การแปลงระหว่างเลขฐานสองและเลขฐานแปด ,การแปลงระหว่างเลขฐานสองและเลขฐานสิบ หก", color: "green" },
  { title: "ตรรกศาสตร์", desc: "ประพจน์ ,การเชื่อมประพจน์ด้วยตัวเชื่อมแบบต่างๆ ,การหาค่าความจริงของประพจน์ ,สัจนิรันดร์ ประพจน์ขัดแย้ง และคอนทิเจน ,การสมมูลกันของประพจน์", color: "purple" },
  { title: "พีชคณิตบูลีน", desc: "เกต (Gate) พื้นฐาน ,การเขียนประพจน์บูลีนจากวงจรลอจิก ,การเขียนวงจรลอจิกจากประพจน์บูลีน ,การหาค่าผลลัพธ์ (Output) ของประพจน์บูลีน ,ทฤษฎีบทของพีชคณิตบูลีน", color: "orange" },
  { title: "เมทริกซ์", desc: "ความหมายและชนิดของเมทริกซ์ ,ทรานสโพสของเมทริกซ์ ,การเท่ากันของเมทริกซ์ ,การบวกและการลบเมทริกซ์ ,การคูณเมทริกซ์ ,ดีเทอร์มิแนนต์ของเมทริกซ์ ,อินเวอร์สการคูณของเมทริกซ์ ,การแก้ระบบสมการเชิงเส้นด้วยเมทริกซ์", color: "red" },
]);

// ข้อมูลเกณฑ์การตัดเกรดที่เพิ่มเข้ามา
const gradingScale = ref([
  { range: "80 - 100", score: "4" },
  { range: "75 - 79", score: "3.5" },
  { range: "70 - 74", score: "3" },
  { range: "65 - 69", score: "2.5" },
  { range: "60 - 64", score: "2" },
  { range: "55 - 59", score: "1.5" },
  { range: "50 - 54", score: "1" },
  { range: "0 - 49", score: "0" },
]);
</script>

<style scoped>
.leading-relaxed {
  line-height: 1.8 !important;
}
.transition-swing {
  transition: 0.3s cubic-bezier(0.25, 0.8, 0.5, 1);
}

.v-card {
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
}

.v-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0,0,0,0.15) !important;
}
</style>