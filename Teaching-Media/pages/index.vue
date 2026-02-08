<template>
  <v-container class="py-8 fill-height align-start bg-tech" fluid>
    
    <v-row justify="center" class="mb-6 animate-fade-down">
      <v-col cols="12" md="10">
        <v-card 
          class="mx-auto overflow-hidden hero-card" 
          elevation="10"
        >
          <v-img
            src="https://images.unsplash.com/photo-1509228468518-180dd4864904?q=80&w=2070&auto=format&fit=crop"
            height="350"
            cover
            class="hero-image-zoom"
            gradient="to bottom, rgba(0,0,0,.2), rgba(0,0,0,.8)"
          >
            <div class="d-flex fill-height flex-column justify-end pa-8 text-white hero-content">
              <div class="hero-text-anim">
                <h1 class="text-h3 font-weight-black mb-1 text-shadow">คณิตศาสตร์คอมพิวเตอร์</h1>
                <h2 class="text-h5 font-weight-light opacity-90 text-cyan-lighten-4">Mathematics for Computer</h2>
                <v-chip label class="mb-3 w-auto" size="large">
                รหัสวิชา 21901-2005
              </v-chip>
              </div>
            </div>
          </v-img>
        </v-card>
      </v-col>
    </v-row>

    <v-row justify="center">
      <v-col cols="12" md="10">
        <v-row>
          <v-col cols="12" md="8" class="animate-slide-right" style="--delay: 0.2s">
            <v-card class="h-100 rounded-lg glass-card" elevation="4" border>
              <v-card-item>
                <template v-slot:prepend>
                  <div class="icon-box-pulse">
                    <v-avatar color="cyan-lighten-5" size="50">
                      <v-icon color="cyan-darken-3" size="30">mdi-book-open-page-variant</v-icon>
                    </v-avatar>
                  </div>
                </template>
                <v-card-title class="text-h5 font-weight-bold text-cyan-darken-4">
                  คำอธิบายรายวิชา
                </v-card-title>
                <v-card-subtitle>Course Description</v-card-subtitle>
              </v-card-item>
              
              <v-divider class="mx-4 opacity-50"></v-divider>

              <v-card-text class="text-body-1 text-grey-darken-3 leading-relaxed pa-6">
                <p style="line-height: 2; text-indent: 40px;">
                  ศึกษาและปฏิบัติเกี่ยวกับ <span class="highlight-text">ระบบจำนวนจริง</span> โครงสร้างและสมบัติของจำนวนจริง 
                  <span class="highlight-text">ระบบเลขฐาน</span> การแปลงเลขฐานสอง ฐานแปด ฐานสิบ และฐานสิบหก 
                  <span class="highlight-text">การคำนวณเลขฐาน</span> การบวก ลบ คูณ หาร และการคอมพลีเมนต์ 
                  หลักการของ <span class="highlight-text">ตรรกศาสตร์</span> ประพจน์ การเชื่อมประพจน์ การหาค่าความจริง การอ้างเหตุผลและสัจนิรันดร์ 
                  <span class="highlight-text">พีชคณิตบูลีน</span> กฎและทฤษฎีบทของบูลีน การลดรูปวงจรลอจิก (Switching Circuit) 
                  และ <span class="highlight-text">เมทริกซ์</span> ดีเทอร์มิแนนต์ อินเวอร์สการคูณ และการประยุกต์ใช้เมทริกซ์ในการแก้ระบบสมการเชิงเส้น
                </p>
              </v-card-text>
            </v-card>
          </v-col>

          <v-col cols="12" md="4" class="animate-slide-left" style="--delay: 0.4s">
            <v-card class="h-100 rounded-lg glass-card-dark" elevation="6" color="cyan-darken-3" theme="dark">
              <v-card-item>
                <template v-slot:prepend>
                  <v-icon size="30" class="mr-2 animate-spin-slow">mdi-target</v-icon>
                </template>
                <v-card-title class="font-weight-bold">จุดประสงค์รายวิชา</v-card-title>
              </v-card-item>
              
              <v-card-text class="pt-2">
                <v-list bg-color="transparent" density="comfortable">
                  <v-list-item v-for="(item, i) in objectives" :key="i" class="objective-item" :style="`--delay: ${0.6 + (i * 0.1)}s`">
                    <template v-slot:prepend>
                      <v-icon color="cyan-accent-2" size="small" class="mt-1">mdi-check-circle-outline</v-icon>
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

        <v-row class="mt-8">
          <v-col cols="12" class="animate-fade-up" style="--delay: 0.8s">
            <h3 class="text-h5 font-weight-bold text-grey-darken-3 mb-4 d-flex align-center section-header">
              <v-icon color="cyan-darken-3" class="mr-2">mdi-layers-triple</v-icon>
              หัวข้อการเรียนรู้ (Topics)
            </h3>
          </v-col>
          
          <v-col 
            v-for="(topic, index) in topics" 
            :key="index" 
            cols="12" sm="6" md="4"
            class="topic-card-wrapper"
            :style="`--delay: ${1 + (index * 0.15)}s`"
          >
            <v-hover v-slot="{ isHovering, props }">
              <v-card 
                v-bind="props"
                :elevation="isHovering ? 12 : 2"
                class="transition-swing rounded-lg border-s-lg h-100 topic-card"
                :class="`border-${topic.color}`"
                :style="`border-left-width: 6px !important;`"
              >
                <v-card-item>
                  <div class="d-flex justify-space-between align-center mb-2">
                    <div class="text-overline font-weight-bold" :class="`text-${topic.color}`">
                      Unit {{ index + 1 }}
                    </div>
                    <v-icon :color="topic.color" :icon="isHovering ? 'mdi-folder-open' : 'mdi-folder'" class="transition-icon"></v-icon>
                  </div>
                  
                  <div class="text-h6 font-weight-bold mb-2 text-grey-darken-3">
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

        <v-row class="mt-8 mb-12">
          <v-col cols="12" class="animate-fade-up" style="--delay: 1.8s">
            <h3 class="text-h5 font-weight-bold text-grey-darken-3 mb-4 d-flex align-center section-header">
              <v-icon color="cyan-darken-3" class="mr-2">mdi-clipboard-check-outline</v-icon>
              เกณฑ์การวัดและประเมินผล
            </h3>
          </v-col>

          <v-col cols="12" md="6" class="animate-fade-up" style="--delay: 2.0s">
            <v-card class="rounded-lg h-100 glass-card" elevation="2" border>
              <v-card-title class="bg-grey-lighten-4 py-3 font-weight-bold text-subtitle-1 d-flex align-center">
                 <v-icon start color="grey-darken-1">mdi-chart-pie</v-icon> สัดส่วนคะแนน
              </v-card-title>
              <v-divider></v-divider>
              <v-list lines="two" class="pa-2">
                <v-list-item class="score-item rounded mb-1">
                  <template v-slot:prepend>
                    <v-avatar color="blue-lighten-5" size="40">
                      <v-icon color="blue-darken-2">mdi-account-star</v-icon>
                    </v-avatar>
                  </template>
                  <v-list-item-title class="font-weight-bold text-blue-darken-2">1. จิตพิสัย</v-list-item-title>
                  <template v-slot:append>
                    <v-chip color="blue" variant="outlined" class="font-weight-bold">20</v-chip>
                  </template>
                </v-list-item>

                <v-list-item class="score-item rounded mb-1">
                  <template v-slot:prepend>
                    <v-avatar color="teal-lighten-5" size="40">
                      <v-icon color="teal-darken-2">mdi-notebook-edit</v-icon>
                    </v-avatar>
                  </template>
                  <v-list-item-title class="font-weight-bold text-teal-darken-2">2. คะแนนระหว่างภาค</v-list-item-title>
                  <v-list-item-subtitle class="text-caption mt-1">
                    แบบทดสอบ(20), แบบฝึกหัด(10), ประเมินผลงาน(10)
                  </v-list-item-subtitle>
                  <template v-slot:append>
                    <v-chip color="teal" variant="outlined" class="font-weight-bold">40</v-chip>
                  </template>
                </v-list-item>

                <v-list-item class="score-item rounded">
                  <template v-slot:prepend>
                    <v-avatar color="deep-purple-lighten-5" size="40">
                      <v-icon color="deep-purple-darken-2">mdi-file-document-edit</v-icon>
                    </v-avatar>
                  </template>
                  <v-list-item-title class="font-weight-bold text-deep-purple-darken-2">3. คะแนนสอบ</v-list-item-title>
                  <v-list-item-subtitle class="text-caption mt-1">กลางภาค (20), ปลายภาค (20)</v-list-item-subtitle>
                  <template v-slot:append>
                    <v-chip color="deep-purple" variant="outlined" class="font-weight-bold">40</v-chip>
                  </template>
                </v-list-item>
              </v-list>
            </v-card>
          </v-col>

          <v-col cols="12" md="6" class="animate-fade-up" style="--delay: 2.2s">
            <v-card class="rounded-lg h-100 glass-card" elevation="2" border>
              <v-table density="comfortable" hover>
                <thead class="bg-grey-lighten-4">
                  <tr>
                    <th class="text-left font-weight-bold">ช่วงคะแนน</th>
                    <th class="text-center font-weight-bold">เกรด</th>
                  </tr>
                </thead>
                <tbody>
                  <tr 
                    v-for="(grade, i) in gradingScale" 
                    :key="grade.range"
                    class="grade-row"
                    :style="`--delay: ${2.4 + (i * 0.05)}s`"
                  >
                    <td class="font-weight-medium text-grey-darken-2 pl-6">{{ grade.range }}</td>
                    <td class="text-center">
                      <v-chip 
                        :color="grade.score >= 3 ? 'green-darken-1' : grade.score >= 1 ? 'orange-darken-1' : 'red-darken-1'" 
                        size="small" 
                        variant="elevated"
                        class="font-weight-bold grade-chip"
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
/* 1. Global Background & Text */
.bg-tech {
  background: radial-gradient(circle at 10% 20%, rgb(242, 246, 252) 0%, rgb(227, 237, 247) 90%);
}
.leading-relaxed { line-height: 1.8 !important; }
.highlight-text {
  color: #00838F; /* Cyan darken 3 */
  font-weight: 600;
  background: rgba(0, 131, 143, 0.05);
  padding: 0 4px;
  border-radius: 4px;
}
.text-shadow { text-shadow: 0 4px 10px rgba(0,0,0,0.5); }

/* 2. Hero Animations */
.hero-card { transform: translateZ(0); } /* Hardware accel */
.hero-image-zoom :deep(img) {
  animation: zoomInOut 20s infinite alternate linear;
  transform-origin: center center;
}
@keyframes zoomInOut {
  0% { transform: scale(1); }
  100% { transform: scale(1.15); }
}

.hero-text-anim {
  opacity: 0;
  animation: fadeUp 1s ease-out 0.3s forwards;
}

/* 3. Entrance Animations (Fade Down/Up/Slide) */
.animate-fade-down {
  opacity: 0;
  animation: fadeDown 0.8s ease-out forwards;
}
.animate-slide-right {
  opacity: 0;
  transform: translateX(-50px);
  animation: slideInRight 0.8s cubic-bezier(0.2, 0.8, 0.2, 1) forwards;
  animation-delay: var(--delay);
}
.animate-slide-left {
  opacity: 0;
  transform: translateX(50px);
  animation: slideInLeft 0.8s cubic-bezier(0.2, 0.8, 0.2, 1) forwards;
  animation-delay: var(--delay);
}
.animate-fade-up {
  opacity: 0;
  transform: translateY(30px);
  animation: fadeUp 0.8s cubic-bezier(0.2, 0.8, 0.2, 1) forwards;
  animation-delay: var(--delay);
}

@keyframes fadeDown {
  from { opacity: 0; transform: translateY(-30px); }
  to { opacity: 1; transform: translateY(0); }
}
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(30px); }
  to { opacity: 1; transform: translateY(0); }
}
@keyframes slideInRight {
  to { opacity: 1; transform: translateX(0); }
}
@keyframes slideInLeft {
  to { opacity: 1; transform: translateX(0); }
}

/* 4. Glass Cards */
.glass-card {
  background: rgba(255, 255, 255, 0.85) !important;
  backdrop-filter: blur(8px);
  border: 1px solid rgba(255,255,255,0.9);
}
.glass-card-dark {
  background: linear-gradient(135deg, #006064 0%, #00838f 100%) !important;
  box-shadow: 0 10px 30px rgba(0, 96, 100, 0.4);
}

/* 5. Icon Effects */
.icon-box-pulse {
  animation: pulse 2s infinite;
}
@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.05); }
  100% { transform: scale(1); }
}
.animate-spin-slow {
  animation: spin 8s linear infinite;
}
@keyframes spin { 100% { transform: rotate(360deg); } }

/* 6. List & Topics Staggering */
.objective-item {
  opacity: 0;
  transform: translateX(20px);
  animation: slideInLeft 0.5s ease forwards;
  animation-delay: var(--delay);
}

.topic-card-wrapper {
  opacity: 0;
  animation: fadeUp 0.6s cubic-bezier(0.25, 1, 0.5, 1) forwards;
  animation-delay: var(--delay);
}

.topic-card {
  transition: all 0.3s cubic-bezier(0.25, 0.8, 0.5, 1);
}
.topic-card:hover {
  transform: translateY(-8px) scale(1.02);
  box-shadow: 0 15px 30px rgba(0,0,0,0.1) !important;
}
.transition-icon { transition: transform 0.3s; }
.topic-card:hover .transition-icon { transform: scale(1.2) rotate(-10deg); }

/* 7. Grading Table Animation */
.grade-row {
  opacity: 0;
  animation: fadeUp 0.4s ease forwards;
  animation-delay: var(--delay);
  transition: background-color 0.2s;
}
.grade-row:hover { background-color: #f5f5f5; }
.grade-chip { transition: transform 0.2s; }
.grade-row:hover .grade-chip { transform: scale(1.2); }

.score-item { transition: transform 0.2s, background-color 0.2s; }
.score-item:hover { transform: translateX(5px); background-color: rgba(0,0,0,0.03); }
</style>