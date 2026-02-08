<template>
  <v-container class="py-12 fill-height align-start gradient-bg" fluid>
    
    <v-row justify="center" class="mb-12 animate-fade-down">
      <v-col cols="12" md="8" class="text-center position-relative">
        <div class="glow-effect"></div>
        
        <h1 class="text-h3 font-weight-bold text-blue-grey-darken-4 mb-2 title-shadow">
          คณะผู้จัดทำ
        </h1>
        <p class="text-h6 text-grey-darken-1 font-weight-light">
          นักศึกษาระดับชั้นประกาศนียบัตรวิชาชีพ (ปวช.)
        </p>
        <v-divider class="my-4 mx-auto divider-anim" length="100" thickness="4" color="primary"></v-divider>
      </v-col>
      <v-row justify="center" class="px-4">
      <v-col 
        v-for="(member, index) in members" 
        :key="index" 
        cols="12" 
        sm="6" 
        md="4"
        lg="3"
        class="member-card-wrapper"
        :style="{ '--delay': `${index * 0.2}s` }" 
      >
        <v-hover v-slot="{ isHovering, props }">
          <v-card
            v-bind="props"
            class="mx-auto rounded-xl pb-4 text-center glass-card"
            :elevation="isHovering ? 16 : 4"
            max-width="350"
            border
          >
            <div class="pt-8 px-6 position-relative">
              <div class="avatar-bg-circle"></div>
              <v-avatar size="200" class="elevation-6 avatar-border">
                <v-img 
                  :src="member.image" 
                  alt="Profile Image" 
                  cover
                  class="zoom-image"
                >
                  <template v-slot:placeholder>
                    <div class="d-flex align-center justify-center fill-height bg-grey-lighten-3">
                      <v-icon color="grey-lighten-1" size="48">mdi-account</v-icon>
                    </div>
                  </template>
                </v-img>
              </v-avatar>
            </div>

            <v-card-item class="pt-6">
              <div class="text-h6 font-weight-bold text-blue-grey-darken-4 mb-1">
                {{ member.name }}
              </div>
              
              <v-chip
                color="primary"
                variant="flat"
                size="small"
                class="mb-4 font-weight-bold px-4"
              >
                ผู้จัดทำ
              </v-chip>

              <v-divider class="mb-4 opacity-50"></v-divider>

              <div class="d-flex justify-center align-center mb-2 info-row">
                <v-icon size="small" color="primary" class="mr-2">mdi-card-account-details-outline</v-icon>
                <span class="text-body-2 text-grey-darken-3">
                  รหัสนักศึกษา: <strong class="text-primary">{{ member.studentId }}</strong>
                </span>
              </div>

              <div class="d-flex justify-center align-center info-row">
                <v-icon size="small" color="primary" class="mr-2">mdi-school-outline</v-icon>
                <span class="text-body-2 text-grey-darken-3">
                  ชั้นปีที่: <strong>3/1</strong>
                </span>
              </div>
            </v-card-item>
          </v-card>
        </v-hover>
      </v-col>
    </v-row>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref } from 'vue';

const members = ref([
  {
    name: "นายปณชัย  พ่วงขำ",
    studentId: "66209010023",
    image: "/img/1.jpg"
  },
  {
    name: "นายสุชัจจ์  รัตนวิเวธน์",
    studentId: "66209010036",
    image: "/img/2.png"
  },
  {
    name: "นายราชพฤกษ์  สลีอ่อน",
    studentId: "66209010028",
    image: "/img/3.png"
  }
]);
</script>

<style scoped>

/* 2. Title Animation (เลื่อนลงมา + จางเข้า) */
.animate-fade-down {
  animation: fadeDown 1s ease-out forwards;
  opacity: 0;
  transform: translateY(-30px);
}

@keyframes fadeDown {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.title-shadow {
  text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
}

/* เส้น Divider ขยายออก */
.divider-anim {
  animation: expandWidth 1.2s ease-out forwards;
  width: 0;
}
@keyframes expandWidth {
  to { width: 100px; }
}

/* 3. Card Entrance Animation (เด้งขึ้นทีละใบ) */
.member-card-wrapper {
  opacity: 0;
  animation: fadeInUp 0.8s cubic-bezier(0.2, 0.8, 0.2, 1) forwards;
  /* ใช้ค่า delay จาก inline style ใน template */
  animation-delay: var(--delay); 
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(60px) scale(0.9);
  }
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

/* 4. Glassmorphism Card Style & Hover */
.glass-card {
  background: rgba(255, 255, 255, 0.9) !important;
  backdrop-filter: blur(10px);
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); /* Bouncy transition */
}

.glass-card:hover {
  transform: translateY(-15px); /* ลอยขึ้นสูง */
}

/* 5. Avatar Styling */
.avatar-border {
  border: 4px solid white;
  transition: transform 0.5s ease;
}

.glass-card:hover .avatar-border {
  transform: scale(1.05); /* รูปขยายเมื่อเอาเมาส์ชี้การ์ด */
  box-shadow: 0 10px 20px rgba(0,0,0,0.15);
}

.zoom-image :deep(img) {
  transition: transform 0.7s ease;
}

.glass-card:hover .zoom-image :deep(img) {
  transform: scale(1.1); /* ซูมรูปภาพข้างใน */
}

/* วงกลมตกแต่งหลัง Avatar */
.avatar-bg-circle {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 210px;
  height: 210px;
  border-radius: 50%;
  background: linear-gradient(45deg, var(--v-theme-primary), #a0e6ff);
  opacity: 0;
  transition: 0.4s;
  z-index: 0;
}

.glass-card:hover .avatar-bg-circle {
  opacity: 0.2;
  width: 230px;
  height: 230px;
}

/* Text Icon Effect */
.info-row {
  transition: transform 0.3s;
}
.glass-card:hover .info-row {
  transform: translateX(5px);
}
</style>